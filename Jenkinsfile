pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES2UG19CS159-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                // Intentional error to fail the pipeline
                sh './output123'  // This command intentionally does not exist
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
