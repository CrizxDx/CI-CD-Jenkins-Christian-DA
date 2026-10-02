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
                    echo "Copiando y listando para asegurar integridad:"
                    cp test_app.py test_run.py
                    ls -la
                    
                    echo "Ejecutando pruebas con unittest:"
                    docker run --rm -v "${WORKSPACE}:/app" -w /app python:3.11-slim python -m unittest test_run.py
                '''
            }
        }
    }
}
