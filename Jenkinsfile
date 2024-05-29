pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh '''
                echo "Building project..." > build.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
                echo "Running tests..." > test.txt
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to development environment...'
                sh '''
                mkdir -p deploy
                cp build.txt test.txt deploy/
                echo "Deployment completed."
                '''
            }
        }
        stage('Push to GitHub') {
            steps {
                echo 'Pushing to GitHub...'
                withCredentials([sshUserPrivateKey(credentialsId: 'cicd', keyFileVariable: 'SSH_KEY')]) {
                    sh '''
                    git config --global user.email "ashmizashah143@gmail.com"
                    git config --global user.name "AshmizaShah"
                    git init
                    git remote add origin git@github.com:AshmizaShah/subtask3.git
                    git add .
                    git commit -m "Add build and test files"
                    git push -u origin main
                    '''
                }
            }
        }
    }
}
