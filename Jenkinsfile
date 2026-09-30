pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out Spring Petclinic code'
            }
        }

        stage('Build') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
