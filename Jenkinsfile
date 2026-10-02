pipeline {
    agent any
    stages {
        stage('Clonar Código del PR') {
            steps {
                checkout scm
            }
        }
        stage('Ejecutar Pruebas Python') {
            steps {
                // Sin atajos ni comandos raros: ejecutamos directamente el archivo de pruebas
                sh 'docker run --rm -v "${WORKSPACE}:/app" -w /app python:3.11-slim python test_app.py'
            }
        }
    }
}
