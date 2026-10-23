
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                bat 'echo Build successful'
            }
        }

        stage('Deploy using SSH') {
            steps {
                sshagent(['deploy-ssh-key']) {
                    bat 'ssh user@yourserver.com "echo Deployed successfully"'
                }
            }
        }

        stage('Deploy using Token') {
            steps {
                withCredentials([
                    string(
                        credentialsId: 'deploy-token',
                        variable: 'TOKEN'
                    )
                ]) {
                    bat 'echo Deploying with a token'
                    // Add your actual deployment/API command here.
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check Console Output.'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
