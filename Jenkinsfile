pipeline {
    agent any

    stages {
        stage('Check Python Path') {
            steps {
                sh 'echo $PATH'
            }
        }
        stage('Check Python Version') {
            steps {
                script {
                    // Check Python 3 version
                    sh 'python3 --version'
                }
            }
        }
        stage('Run Python Script') {
            steps {
                script {
                    // Run a Python script to display "Hello, world!"
                    sh 'echo "print(\\"Hello, world!\\")" > script.py'
                    sh 'python3 script.py'
                }
            }
        }
    }
}
