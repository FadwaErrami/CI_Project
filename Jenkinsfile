pipeline {
    agent any

    environment {
        PYTHON = 'C:\\Users\\hp\\AppData\\Local\\Programs\\Python\\Python311\\python.exe'
    }

    stages {
        stage('Vérification Python') {
            steps {
                bat '%PYTHON% --version'
                bat '%PYTHON% -m pip --version'
            }
        }

        stage('Installation des dépendances') {
            steps {
                bat '%PYTHON% -m pip install -r requirements.txt'
            }
        }

        stage('Tests unitaires') {
            steps {
                bat '%PYTHON% -m pytest'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminé'
        }
        success {
            echo 'BUILD SUCCESS'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}
