pipeline {
    agent any

    environment {
        REMOTE_USER = "ericdt17"
        REMOTE_HOST = "ssh-ericdt17.alwaysdata.net "
        REMOTE_PATH = "/home/ericdt17/www/"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building..."
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'alwaysdata-ssh',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh '''
                    sshpass -p "$PASS" scp -o StrictHostKeyChecking=no -r * ericdt17@ssh-ericdt17.alwaysdata.net:/home/ericdt17/www/
                    '''
                }
            }
        }
    }
}
