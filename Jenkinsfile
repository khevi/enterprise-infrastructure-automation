pipeline {
    agent any

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
                    khevi@192.168.40.9 hostname
                '''
            }
        }

        stage('Verify Ansible') {
            steps {
                sh '''
                    ssh khevi@192.168.40.9 \
                    "cd ~/enterprise-infrastructure-automation && ansible --version"
                '''
            }
        }

        stage('Ansible Inventory Test') {
            steps {
                sh '''
                    ssh khevi@192.168.40.9 \
                    "cd ~/enterprise-infrastructure-automation && ansible linux -m ping"
                '''
            }
        }

        stage('Syntax Check') {
            steps {
                sh '''
                    ssh khevi@192.168.40.9 \
                    "cd ~/enterprise-infrastructure-automation && \
                    ansible-playbook playbooks/nginx-container.yml --syntax-check"
                '''
            }
        }

        stage('Verify Application') {
            steps {
                sh '''
                    curl --fail --silent --show-error \
                    http://192.168.40.10:8080 > /dev/null
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed. Review the stage logs.'
        }
    }
}
