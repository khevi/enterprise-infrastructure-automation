pipeline {
    agent any

    environment {
        CONTROLLER   = 'khevi@192.168.40.9'
        DEPLOY_DIR   = '/home/khevi/jenkins-deploy/enterprise-infrastructure-automation'
        REPOSITORY   = 'https://github.com/khevi/enterprise-infrastructure-automation.git'
        DEPLOY_BRANCH = 'feature/jenkins-deployment'
        APP_URL      = 'http://192.168.40.10:8080'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Controller Access') {
            steps {
                sh '''
                    ssh -o StrictHostKeyChecking=accept-new \
                        "$CONTROLLER" hostname
                '''
            }
        }

        stage('Synchronize Deployment Repository') {
            steps {
                sh '''
                    ssh "$CONTROLLER" "
                        set -e

                        if [ ! -d '$DEPLOY_DIR/.git' ]; then
                            mkdir -p /home/khevi/jenkins-deploy
                            git clone '$REPOSITORY' '$DEPLOY_DIR'
                        fi

                        cd '$DEPLOY_DIR'
                        git fetch origin '$DEPLOY_BRANCH'
                        git checkout -B '$DEPLOY_BRANCH' \
                            'origin/$DEPLOY_BRANCH'
                    "
                '''
            }
        }

        stage('Ansible Syntax Check') {
            steps {
                sh '''
                    ssh "$CONTROLLER" "
                        cd '$DEPLOY_DIR' &&
                        ansible-playbook \
                            playbooks/nginx-container.yml \
                            --syntax-check
                    "
                '''
            }
        }

        stage('Deploy Nginx') {
            steps {
                sh '''
                    ssh "$CONTROLLER" "
                        cd '$DEPLOY_DIR' &&
                        ansible-playbook \
                            playbooks/nginx-container.yml
                    "
                '''
            }
        }

        stage('Verify Container') {
            steps {
                sh '''
                    ssh "$CONTROLLER" "
                        cd '$DEPLOY_DIR' &&
                        ansible app \
                            -m shell \
                            -a 'docker ps --filter name=web-lab2'
                    "
                '''
            }
        }

        stage('Application Health Check') {
            steps {
                sh '''
                    curl --fail \
                         --silent \
                         --show-error \
                         --retry 5 \
                         --retry-delay 3 \
                         "$APP_URL" > /dev/null
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }

        failure {
            echo 'Deployment failed. Review the stage logs.'
        }
    }
}
