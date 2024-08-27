pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Shava173/Jenkins_CI-CD.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to test server...'
                // Додайте команди для деплою, якщо необхідно
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
