pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Spring Boot App') {
            steps {
                sh './build.sh'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-service .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -p 8081:8081 student-service'
            }
        }
    }
}