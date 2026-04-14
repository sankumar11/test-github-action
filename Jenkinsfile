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
                echo "Building branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }
        stage('JSM Triggered Job') {
            when {
                expression {
                    return params.JSM_TRIGGER == 'true'
                }
            }
            steps {
                echo "Triggered from Jira"
            }
        }
    }
}
