pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    environment {
        // variables defined here can be used in any stage
        NEW_VERSION = '1.3.0'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}"
                bat 'nvm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deployment commands here
            }
        }

    }
}
