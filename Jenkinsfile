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
                    scp /home/ubuntu/jenkins/workspace/project/index.html ubuntu@65.0.80.119:/tmp/
                    ssh ubuntu@65.0.80.119 "sudo cp /tmp/index.html /var/www/html/"
                '''
            }
        }
    }
}
