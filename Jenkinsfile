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
                withCredentials([sshUserPrivateKey(credentialsId: 'github-ssh-key', keyFileVariable: 'SSH_KEY')]) {
                    sh '''
                    git config --global user.email "you@example.com"
                    git config --global user.name "Your Name"
                    git init
                    git remote add origin git@github.com:AshmizaShah/test.git
                    git add .
                    git commit -m "Add build and test files"
                    git push -u origin main
                    '''
                }
            }
        }
    }
}
