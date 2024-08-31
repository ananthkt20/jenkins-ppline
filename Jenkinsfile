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
    always {
        emailext to: 'ananthkt865@gmail.com',
                 subject: 'Jenkins Pipeline Build Status: ${currentBuild.currentResult}',
                 body: "Build status: ${currentBuild.currentResult}\nCheck the Jenkins build at: ${env.BUILD_URL}"
    }
}

}
