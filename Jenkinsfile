pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'hazelnelthropp', url: 'https://github.com/hazelnelthropp/Mico-Hospital.git'
            }
        }
        stage('Deploy') {
            steps {
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
