pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile the .cpp file using the build script
                build 'PES1UG21CS077-1'
                sh 'g++ new_file.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                // Print output of the .cpp file using a shell script
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                // Commands to deploy the application
              echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'pipeline failed'
        }
    }
}
