pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/hemanth3103/Royal-Respite'
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('Royal-Respite-main') { // 👈 if your Dockerfile is inside this subfolder
                    bat 'docker build -t royal-respite .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 3000:3000 --name royal-respite-container royal-respite'
            }
        }
    }
}
