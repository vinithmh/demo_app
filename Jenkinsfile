pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                script {
                    // Check if Dockerfile exists in the root directory
                    if (fileExists('Dockerfile')) {
                        // Build the application using Dockerfile
                        sh 'docker build -t demo_jenkins_app .'
                    } else {
                        error 'Dockerfile not found in the root directory of the repository.'
                    }
                }
            }
        }
    }
}
