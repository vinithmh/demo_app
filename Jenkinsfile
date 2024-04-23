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
        
        stage('Run Build Image') {
            steps {
                script {
                    // Run the built Docker image
                    sh 'docker run -d -p 8080:80 demo_jenkins_app'
                }
            }
        }
    }
}
