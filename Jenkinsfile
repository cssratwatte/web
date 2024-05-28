pipeline {
    agent any
    
    stages {
        stage('Declarative: Checkout SCM - 725ms') {
            steps {
                echo 'Checking out SCM...'
                checkout scm
            }
        }
        stage('Build - 28ms') {
            steps {
                echo 'Building the code...'
                // Add your build commands here, e.g., Maven or Gradle build
            }
        }
        stage('Test - 1s') {
            steps {
                echo 'Running unit tests...'
                // Add your unit test commands here, e.g., JUnit tests
                echo 'Running integration tests...'
                // Add your integration test commands here
            }
            post {
                success {
                    mail to: "chathurniratwatte@gmail.com",
                        subject: "Build Status - SUCCESS",
                        body: "Unit and integration tests were successful!"
                }
                failure {
                    mail to: "chathurniratwatte@gmail.com",
                        subject: "Build Status - FAILURE",
                        body: "Unit and integration tests failed!"
                }
            }
        }
        stage('Code Quality Analysis - 5s') {
            steps {
                echo 'Performing code quality analysis...'
                // Add your code quality analysis commands here, e.g., SonarQube
            }
        }
        stage('Deploy to Test Environment - 1m 35s') {
            steps {
                echo 'Deploying to test environment...'
                // Add your deployment commands here, e.g., Docker Compose or AWS Elastic Beanstalk
            }
        }
        stage('Release - 10s') {
            steps {
                echo 'Releasing the application...'
                // Add your release commands here, e.g., Octopus Deploy or AWS CodeDeploy
            }
        }
        stage('Monitoring and Alerting - 34s') {
            steps {
                echo 'Setting up monitoring and alerting...'
                // Add your monitoring and alerting commands here, e.g., Datadog or New Relic
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Add any cleanup commands here
        }
        success {
            echo 'Build was successful!'
            mail to: "chathurniratwatte@gmail.com",
                subject: "Pipeline Status - SUCCESS",
                body: "The pipeline completed successfully."
        }
        failure {
            echo 'Build failed!'
            mail to: "chathurniratwatte@gmail.com",
                subject: "Pipeline Status - FAILURE",
                body: "The pipeline failed."
        }
    }
}
