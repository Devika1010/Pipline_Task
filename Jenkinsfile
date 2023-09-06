pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Use Maven to build the code
                bat 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests (modify the command as needed)
                bat 'mvn test'

                // Run integration tests (modify the command as needed)
                bat 'mvn integration-test'
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate code analysis tool (e.g., SonarQube)
                bat 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                // Perform security scan (replace with your security scanning tool)
                bat 'security-scan-command'
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy to staging environment (e.g., AWS EC2 instance)
                bat 'deploy-to-staging-command'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on the staging environment
                bat 'run-integration-tests-on-staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy to production environment (e.g., AWS EC2 instance)
                bat 'deploy-to-production-command'
            }
        }
    }

    post {
        failure {
            // Send email notification on pipeline failure
            emailext subject: "Pipeline Failed",
                body: "The Jenkins pipeline has failed. Please investigate.",
                to: 'sivakumardevika028@gmail.com'
        }
        success {
            // Send email notification on pipeline success
            emailext subject: "Pipeline Successful",
                body: "The Jenkins pipeline has completed successfully.",
                to: 'sivakumardevika028@gmail.com'
        }
    }
}
