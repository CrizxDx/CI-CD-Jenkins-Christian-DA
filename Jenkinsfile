pipeline {
    agent any
    stages {
        stage('Clonar Código del PR') {
            steps {
                // Al usar Multibranch Pipeline, checkout scm descarga automáticamente el código del PR
                checkout scm
            }
        }
        stage('Ejecutar Pruebas Python') {
            steps {
                sh '''
                    docker run --rm -v $ (pwd):/app -w /app \
                    python:3.11-slim python -m unittest test_app.py
                  '''
            }
        }
    }
}
