pipeline {
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Checkout the source code from GitHub'
                git url: 'https://github.com/hazelnelthropp/Mico-Hospital.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'copy.yml',
                    inventory: 'dev.inv',
                    credentialsId: 'd22c5698-5f03-4724-bfc2-83430bd6406f',
                    disableHostKeyChecking: true,
                    installation: 'ansible'
                )
            }
        }
    }
}
