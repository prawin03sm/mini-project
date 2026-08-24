pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'YOUR_GITHUB_REPOSITORY'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    scp index.html ubuntu@3.110.161.31:/tmp/
                    ssh ubuntu@3.110.161.31 "sudo cp /tmp/index.html /var/www/html/"
                '''
            }
        }
    }
}
