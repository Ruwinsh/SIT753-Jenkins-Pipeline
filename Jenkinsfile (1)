pipeline {
    agent any

    triggers {
        // Poll GitHub for new commits every ~2 minutes (no webhook needed)
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile the source code and package it into a deployable artefact.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests to verify individual functions, and integration tests to verify components work together.'
                echo 'Tools: JUnit (unit tests), Selenium (integration tests)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse the code for quality, bugs, code smells and adherence to industry standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Task: Scan the code and its dependencies to identify known security vulnerabilities.'
                echo 'Tool: Snyk'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the application to a staging server.'
                echo 'Tool: AWS CodeDeploy (target: AWS EC2 staging instance)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests against the staging environment to confirm the app works in a production-like setting.'
                echo 'Tool: Postman (Newman CLI)'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the application to the production server.'
                echo 'Tool: AWS CodeDeploy (target: AWS EC2 production instance)'
            }
        }
    }
}
