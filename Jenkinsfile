pipeline {
    agent any
    
    environment {
        // Define environment variables here
        APP_NAME = 'devops_101'
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building application...'
                // Add your build commands here
                // Example: sh 'npm install' or sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here
                // Example: sh 'npm test' or sh 'mvn test'
            }
        }
        
        stage('Code Quality') {
            steps {
                echo 'Running code quality checks...'
                // Add code quality tools here
                // Example: sh 'npm run lint' or sh 'sonar-scanner'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment commands here
                // Example: sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            echo 'Cleaning up...'
            cleanWs()
        }
    }
}
