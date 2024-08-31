pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                // Example command to build the code
                // sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example command to run tests
                // sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
                // Example command to run code analysis
                // sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example command for security scan
                // sh 'dependency-check --project my-app --scan .'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
                // Example command to deploy to staging
                // sh 'scp target/my-app.jar user@staging-server:/path/to/deploy'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on Staging environment...'
                // Example command for integration tests
                // sh 'mvn verify -Denv=staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production environment...'
                // Example command to deploy to production
                // sh 'scp target/my-app.jar user@production-server:/path/to/deploy'
            }
        }
    }

   post {
        success {
            emailext(
                to: 'ananthkt865@gmail.com',
                subject: "Jenkins Build Successful: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>Good news! The Jenkins build <strong>${env.JOB_NAME} #${env.BUILD_NUMBER}</strong> was successful.</p>
                         <p>Check the details: ${env.BUILD_URL}</p>""",
                mimeType: 'text/html'
            )
        }
        failure {
            emailext(
                to: 'ananthkt865@gmail.com',
                subject: "Jenkins Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>Unfortunately, the Jenkins build <strong>${env.JOB_NAME} #${env.BUILD_NUMBER}</strong> failed.</p>
                         <p>Check the details: ${env.BUILD_URL}</p>""",
                mimeType: 'text/html'
            )
        }
    }
}
