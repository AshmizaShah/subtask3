pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to development environment...'
            }
        }
        stage('Python Version Check') {
            steps {
                echo 'Checking Python version...'
                sh 'python version_check.py'
            }
        }
        stage('Push to GitHub') {
            steps {
                echo 'Pushing to GitHub...'
                // Add Git push commands here
            }
        }
    }
}
