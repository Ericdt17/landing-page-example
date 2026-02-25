pipeline {
    agent { label 'linux' }

    stages {
        stage('Run on Agent') {
            steps {
                sh 'echo "Je tourne sur l’agent"'
                sh 'whoami'
                sh 'hostname'
            }
        }
    }
}
