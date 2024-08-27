pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Shava173/Jenkins_CI-CD.git'
            }
        }

        stage('Build') {
            steps {
                // Використання Maven для побудови проекту
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Запуск тестів
                sh 'mvn test'
            }
            post {
                always {
                    // Збір результатів тестів
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to test server...'
                // Тут можна додати реальні команди для деплою на тестовий сервер
                // наприклад, команди для копіювання файлів на сервер
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
