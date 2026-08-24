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
                    mkdir -p ~/.ssh
                    ssh-keyscan -H 13.207.84.78 >> ~/.ssh/known_hosts
                    scp /home/ubuntu/jenkins-agent/workspace/Build/index.html ubuntu@13.207.84.78:/tmp/
                    ssh ubuntu@13.207.84.78 "sudo cp /tmp/index.html /var/www/html/"
                '''
            }
        }
    }
}
