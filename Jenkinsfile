pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Aditya252006/Devops_Test.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-nginx .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f jenkins-nginx || true
                docker run -d -p 80:80 --name jenkins-nginx jenkins-nginx
                '''
            }
        }
    }
}
