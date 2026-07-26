pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying from branch: ${env.BRANCH_NAME}"
            }
        }
    }

    post {
        success {
            echo "Build Successful!"
        }

        failure {
            echo "Build Failed!"
        }
    }
}
