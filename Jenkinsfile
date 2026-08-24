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
                    scp /home/ubuntu/jenkins-agent/workspace/Build/index.html ubuntu@10.0.0.8:/tmp/
                    ssh ubuntu@10.0.0.29 "sudo cp /tmp/index.html /var/www/html/"
                '''
            }
        }
    }
}
