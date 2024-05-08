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
                    privateKey: 'jenkins-2.pem',
                    ansibleName: 'Ansible'
                )
            }
        }
    }
}
