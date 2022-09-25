pipeline {
    agent {agent}

    stages {
        
           stage('Step0 - Git Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vishaldpw/jenkins-docker']]])
            }
        }
        
        stage('Step1 .. Check Docker ') {
            steps {
                sh '''docker ps
                    docker -v'''
            }
        }

        stage('Step2 .. Docker compose UP') {
            steps {
                sh 'docker compose up -d --no-color --wait'
            }
        }
        
        stage('Step3 .. Docker compose ps') {
            steps {
                sh 'docker compose ps'
            }
        }
    }
}
