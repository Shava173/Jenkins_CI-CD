pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Перевіряємо підключення до Git
                    try {
                        git branch: 'main', url: 'https://github.com/Shava173/Jenkins_CI-CD.git'
                        echo "Git repository checked out successfully"
                    } catch (Exception e) {
                        error "Failed to checkout Git repository: ${e.getMessage()}"
                    }
                }
            }
        }
        stage('List Files') {
            steps {
                script {
                    // Перевіряємо, чи файли були завантажені успішно
                    sh 'ls -al'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for more details.'
        }
    }
}
