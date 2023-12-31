pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Running Build Stage'
                echo 'Command: mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests Stage'
                echo 'Command: mvn test'
                echo 'Command: mvn integration-test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis Stage'
                echo 'Command: sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan Stage'
                echo 'Command: security-scan-command'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Running Deploy to Staging Stage'
                echo 'Command: deploy-to-staging-command'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging Stage'
                echo 'Command: run-integration-tests-on-staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Running Deploy to Production Stage'
                echo 'Command: deploy-to-production-command'
            }
        }
    }

    post {
        failure {
            // Send email notification on pipeline failure
            emailext attachLog: true,
             subject: "Pipeline Failed",
                body: "The Jenkins pipeline has failed.Check it",
                to: 'sivakumardevika028@gmail.com'
        }
        success {
            // Send email notification on pipeline success
             emailext attachLog: true,
             subject: "Pipeline Successful",
                body: "The Jenkins pipeline has completed successfully.",
                to: 'sivakumardevika028@gmail.com'
        }
    }
}
