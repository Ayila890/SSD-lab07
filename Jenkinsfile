pipeline {
    agent any

    parameters {
        // Different types of parameters
        string(
            name: 'VERSION',
            defaultValue: '',
            description: 'Version to deploy on prod'
        )

        choice(
            name: 'ENV_VERSION',
            choices: ['1.1.0', '1.2.0', '1.3.0'],
            description: 'Select version for environment'
        )

        booleanParam(
            name: 'executeTests',
            defaultValue: true,
            description: 'Enable or disable test stage'
        )
    }

    environment {
        // Variables accessible in any stage
        NEW_VERSION = '1.3.0'
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Project..."
                echo "Using environment version: ${NEW_VERSION}"
                echo "User entered version: ${params.VERSION}"

                // Example build command
                sh "echo Building version ${params.ENV_VERSION}"
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo "Testing Project..."
                sh "echo Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${params.VERSION} ..."
                sh "echo Deploying to production environment"
            }
        }
    }
}
