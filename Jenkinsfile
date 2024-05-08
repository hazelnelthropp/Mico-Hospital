pipeline {
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Checkout the source code from GitHub'
                git 'https://github.com/kranthi619/med-pro.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                // Run ansible playbook
                ansiblePlaybook(
                    credentialsId: '76c38d7d-75d8-4180-b101-5fa4acb4750b',
                    disableHostKeyChecking: true,
                    installation: 'ansible',
                    inventory: 'dev.inv',
                    playbook: 'copy.yml'
                )
            }
        }
    }
}
