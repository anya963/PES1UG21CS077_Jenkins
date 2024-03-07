pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Commands to build the project
                sh 'make build'
            }
        }
        stage('Test') {
            steps {
                // Commands to run tests
                sh 'make test'
            }
        }
        stage('Deploy') {
            steps {
                // Commands to deploy the application
                sh 'make deploy'
            }
        }
    }

    post {
        failure {
            echo 'pipeline failed'
        }
    }
}
