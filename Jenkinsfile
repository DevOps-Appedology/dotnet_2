
## Commit  tessss
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Your build steps go here//
                
                // Print a message during the build step
                echo 'Building the project...'
            }//
        }////
        stage('Test') {
            steps {
                // Your test steps go here
                
                // Print a message during the test step
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                // Your deployment steps go here
                
                // Print a message during the deployment step
                echo 'Deploying the application...'
            }
        }
    }
    
    post {
        success {
            // Actions to perform on successful build
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to perform on build failure
            echo 'Pipeline failed!'
        }
    }
}
