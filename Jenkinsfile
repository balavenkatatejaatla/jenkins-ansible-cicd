pipeline {
    agent any

    environment {
        ANSIBLE_VAULT_PASSWORD = credentials('ansible-vault-password')
    }

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['development', 'staging', 'production'],
            description: 'Choose the environment to deploy to'
        )
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/balavenkatatejaatla/jenkins-ansible-cicd.git'
            }
        }
        stage('Install Ansible') {
            steps {
                sh '''
                sudo apt update
                sudo apt install -y ansible
                '''
            }
        }
        stage('Deploy to Environment') {
            steps {
                script {
                    def inventoryFile = "inventory/${params.ENVIRONMENT}"
                    ansiblePlaybook credentialsId: 'your-ssh-key-credentials-id', disableHostKeyChecking: true, installation: 'Ansible', inventory: inventoryFile, playbook: 'playbook.yml', extras: '--vault-password-file /path/to/vault-password-file'
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
