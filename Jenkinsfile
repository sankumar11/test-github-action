pipeline {
    agent any
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'issue_key',  value: '$.issue_key'],
                [key: 'summary',    value: '$.summary'],
                [key: 'status',     value: '$.status'],
                [key: 'reporter',   value: '$.reporter'],
                [key: 'priority',   value: '$.priority'],
                [key: 'assignee',   value: '$.assignee']
            ],
            token: 'jsm-token',
            printContributedVariables: true,
            printPostContent: true
        )
    }
    stages {
        stage('Print Jira Details') {
            steps {
                echo "=================================="
                echo "Issue Key  : ${env.issue_key}"
                echo "Summary    : ${env.summary}"
                echo "Status     : ${env.status}"
                echo "Reporter   : ${env.reporter}"
                echo "Priority   : ${env.priority}"
                echo "Assignee   : ${env.assignee}"
                echo "=================================="
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }

//         stage('Build') {
//             steps {
//                 echo "Building branch: ${env.BRANCH_NAME}"
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo "Running tests..."
//             }
//         }
//         stage('JSM Triggered Job') {
//             when {
//                 expression {
//                     return params.JSM_TRIGGER == 'true'
//                 }
//             }
//             steps {
//                 echo "Triggered from Jira"
//             }
//         }
//     }
// }
