pipeline {
    agent { label 'docker-agent-python' }

    triggers {
        pollSCM('* * * * *')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.image('python:3.10-slim').inside {
                        sh '''
                        echo "Build stage"
                        python --version
                        '''
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('python:3.10-slim').inside {
                        sh '''
                        echo "Test stage"
                        python helloworld.py
                        '''
                    }
                }
            }
        }

        stage('Deliver') {
            steps {
                script {
                    docker.image('python:3.10-slim').inside {
                        sh '''
                        echo "Deliver stage"
                        echo "Deploy logic goes here"
                        '''
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
