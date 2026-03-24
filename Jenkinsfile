pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Use your actual branch name and credentials ID here
                git branch: 'master', 
                    url: 'https://github.com/Mayur-2403/combo-lab4-2.git', 
                    credentialsId: 'github-credentials'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("flask-app-image:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run('-p 5000:5000')
                }
            }
        }
    }
}
