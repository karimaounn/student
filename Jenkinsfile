pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Spring Boot App') {
            steps {
                bat 'mvnw package'
                bat 'mkdir -p target/dependency && (cd target/dependency; jar -xf ../*.jar)'
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