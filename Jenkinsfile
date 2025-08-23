pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mvn clean install'   // For Java-Maven project
                // sh 'npm install'      // For Node.js project
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'            // Or 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Example:
                // sh 'scp target/*.jar user@server:/deploy/path/'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs.'
        }
    }
}
