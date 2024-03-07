pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output PES1UG21CS077.cpp'
                    echo 'Build Stage Successful'
                }
            }
            post {
                always {
                    catchError {
                        sh 'echo "Build stage completed"'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './outputs'
                    echo 'Test Stage Successful'
                }
            }
            post {
                always {
                    catchError {
                        sh 'echo "Test stage completed"'
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
            post {
                always {
                    catchError {
                        sh 'echo "Deploy stage completed"'
                    }
                }
            }
        }
    }
    post {
        always {
            catchError {
                echo 'Pipeline failed'
            }
        }
    }
}
