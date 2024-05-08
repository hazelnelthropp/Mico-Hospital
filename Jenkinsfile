pipeline {
    agent any

    stages {
        stage('git clone') {
            steps {
            git 'https://github.com/hazelnelthropp/Mico-Hospital.git'
            }
        }

        stage('build') {
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
