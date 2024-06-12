pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the code from the repository
                    checkout scm
                }
            }
        }
        stage('Print Branch and Commit ID') {
            steps {
                script {
                    // Get the branch name and commit ID
                    def branchName = env.BRANCH_NAME
                    def commitId = sh(script: 'git rev-parse HEAD', returnStdout: true).trim()
                    
                    // Print the branch name and commit ID
                    echo "BUILD DETAILS"
                    echo "Branch Name: ${branchName}"
                    echo "Commit ID: ${commitId}"
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline finished for branch: ${env.BRANCH_NAME}"
        }
    }
}
