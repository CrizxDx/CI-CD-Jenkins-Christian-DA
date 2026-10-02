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
                sh '''
                    echo "Revisando contenido actual de la carpeta:"
                    ls -la
                    
                    echo "Ejecutando pruebas..."
                    docker run --rm -v "${WORKSPACE}:/app" -w /app python:3.11-slim python test_app.py
                '''
            }
        }
    }
}
