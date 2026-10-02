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
                    echo "Buscando archivos de prueba en el workspace:"
                    find . -name "test_app.py"
                    
                    echo "Ejecutando la prueba con Python:"
                    docker run --rm -v "${WORKSPACE}:/app" -w /app python:3.11-slim python -m unittest $(find . -name "test_app.py" | sed 's|./||' | sed 's/\.py//' | tr '/' '.')
                '''
            }
        }
    }
}
