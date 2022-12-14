pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-19\\bin'
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Spring Boot App') {
            steps {
                bat 'build.bat'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker.build.bat'
            }
        }
        stage('Run Docker Container') {
            steps {
                bat 'docker.run.bat'
            }
        }
    }
}