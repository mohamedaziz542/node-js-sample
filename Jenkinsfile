pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                // Add commands to run tests
                sh 'echo "Running tests"'
            }
        }
        stage('Dockerize') {
            steps {
                script {
                    def app = docker.build("myapp/nodejs-app:${env.BUILD_ID}")
                    app.push()
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying application"'
                // Use kubectl or helm to deploy your application
                // For example, update your Kubernetes deployment image
            }
        }
    }
}
