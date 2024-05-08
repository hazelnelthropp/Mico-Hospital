pipeline {
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Checkout the source code from GitHub'
                git 'https://github.com/hazelnelthropp/Mico-Hospital.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'copy.yml',            // Ensure this path is correct
                    inventory: 'dev.inv',            // Adjust if necessary
                    credentialsId: '76c38d7d-75d8-4180-b101-5fa4acb4750b',
                    disableHostKeyChecking: true,
                    installation: 'ansible'
                )
            }
        }
    }
}
