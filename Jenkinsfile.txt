pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "D:\\University\\Deakin\\DS\\T2\\SIT753-Professional Practice in IT\\seminar 5\\code"
        TESTING_ENVIRONMENT = "env-stg"
        PRODUCTION_ENVIRONMENT = "Pooya Forghani Arani"
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetch code from ${env.DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
            }
        }
        stage('Test') {
            steps {
                echo "unit tests"
                echo "integration tests"
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "check the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy the application to ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                sleep(time:10, unit: "SECONDS")
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
