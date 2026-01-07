pipeline {
    agent {
        docker {
            image 'python:3.10-slim'
        }
    }

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build stage'
                sh 'python --version'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage'
                sh 'python helloworld.py'
            }
        }

        stage('Deliver') {
            steps {
                echo 'Deliver stage'
                sh 'echo delivery done'
            }
        }
    }
}
