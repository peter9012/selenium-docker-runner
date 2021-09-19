pipeline {
    agent any
    stages {
        stage('Start Grid') {
            steps {
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Run Test') {
            steps {
                sh "docker-compose up search-module book-flight-module1 book-flight-module2"
            }
        }
        stage('Stop Grid') {
            steps {
                sh "docker-compose down"
            }
        }
    }
}