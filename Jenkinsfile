pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Шаг для получения исходного кода из репозитория
                git 'https://github.com/Podmoskovnykh/cpp-hello-world.git'
            }
        }

        stage('Build') {
            steps {
                // Шаг для компиляции исходного кода
                script {
                    sh 'g++ main.cpp -o main'
                }
            }
        }

        stage('Archive') {
            steps {
                // Шаг для создания артефакта (бинарного файла)
                archiveArtifacts 'main'
            }
        }
    }

    post {
        success {
            // Шаги, которые выполнятся при успешном завершении пайплайна
            echo 'Build successful. Artifacts are ready.'
        }
        failure {
            // Шаги, которые выполнятся при ошибке во время выполнения пайплайна
            echo 'Build failed. Please check the build logs for details.'
        }
    }
}
