pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git url: 'https://github.com/Akhil554/portfolio-website.git', branch: 'main'

            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-portfolio')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop my-portfolio || true'
                sh 'docker rm my-portfolio || true'
                sh 'docker run -d --name my-portfolio -p 8082:80 my-portfolio'
            }
        }
    }
}
