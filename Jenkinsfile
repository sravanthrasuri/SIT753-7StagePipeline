pipeline {
    agent any

    triggers {
        pollSCM('H/1 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package the application.'
                echo 'Tool: Apache Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests and confirm that application components work together.'
                echo 'Tools: JUnit for unit testing and Selenium for integration testing'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse code quality, coding standards, bugs and code smells.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan the source code and dependencies for known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the application to a staging environment for testing.'
                echo 'Tool: AWS CLI with an AWS EC2 staging instance'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Test the application in a production-like staging environment.'
                echo 'Tool: Postman and Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the approved application to the production server.'
                echo 'Tool: AWS CodeDeploy with an AWS EC2 production instance'
            }
        }
    }

    post {
        success {
            echo 'The complete seven-stage mock pipeline executed successfully.'
        }

        failure {
            echo 'The pipeline failed. Check the console output.'
        }
    }
}
