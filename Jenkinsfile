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
                sh ' docker run --rm -v /opt/jenkins_home/workspace/CI-CD-PullRequests_main:/app \
                -w /app \
                python:3.11-slim \
                python -m unittest test_app.py'
            }
        }
    }
}
