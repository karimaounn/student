pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-19'
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Spring Boot App') {
            steps {
                bat 'mvnw package'
                bat 'mkdir.exe -p target/dependency'
                bat 'cd.exe target/dependency'
                bat 'jar -xf ../*.jar'
            }
        }
        // stage('Build Docker Image') {
        //     steps {
        //         sh 'docker build -t student-service .'
        //     }
        // }
        // stage('Run Docker Container') {
        //     steps {
        //         sh 'docker run -p 8081:8081 student-service'
        //     }
        // }
    }
}