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
                sh "docker-compose up search-module book-flight-module"
            }
        }
    }
    post {
        always{
            archiveArtfacts artfacts: 'output/**'
            sh "docker-compose down"
        }
    }
}