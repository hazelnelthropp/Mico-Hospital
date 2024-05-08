pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'hazelnelthropp', url: 'https://github.com/hazelnelthropp/Mico-Hospital.git'
            }
        }
        stage('Deploy') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'd22c5698-5f03-4724-bfc2-83430bd6406f',
                    disableHostKeyChecking: true,
                    installation: 'ansible',
                    inventory: 'dev.inv',
                    playbook: 'copy.yml'
                )
            }
        }
    }
}
