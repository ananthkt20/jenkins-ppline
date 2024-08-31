pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'

            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
              
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
               
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
          
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
          
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on Staging environment...'
            
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production environment...'
            
            }
        }
    }

    post {
        always {
            emailext(
                to: 'ananthkt865@gmail.com',
                subject: "Jenkins Pipeline Build Status: ${currentBuild.currentResult}",
                body: """Build status: ${currentBuild.currentResult}
                Check the Jenkins build at: ${env.BUILD_URL}"""
            )
        }
    }
}
