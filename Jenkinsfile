pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                // Fetch code from Git repository using credentials
                git credentialsId: 'hazelnelthropp', url: 'https://github.com/hazelnelthropp/Mico-Hospital.git'
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
