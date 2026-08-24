pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/prawin03sm/mini-project.git'
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
                    scp index.html ubuntu@13.207.84.78:/tmp/
                    ssh ubuntu@3.110.161.31 "sudo cp /tmp/index.html /var/www/html/"
                '''
            }
        }
    }
}
