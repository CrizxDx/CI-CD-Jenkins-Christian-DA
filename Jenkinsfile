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
                    cp test_app.py test_run.py
                    ls -la
                    docker run --rm -v /opt/jenkins_home/workspace/CI-CD-PullRequests_main:/app \
                -w /app \
                python:3.11-slim \
                python test_run.py
        '''
            }
        }
    }
