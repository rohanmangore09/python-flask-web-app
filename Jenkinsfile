pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
               git branch: 'main', url: 'https://github.com/rohan11131113/python-flask-web-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build('flask-ci-cd-project')
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    dockerImage.run('-p 5000:5000')
                }
            }
        }
    }
}
