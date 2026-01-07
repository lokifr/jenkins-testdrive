pipeline {
    agent { label 'docker-agent-python' }

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "Nothing to build for now"
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                python3 helloworld.py
                '''
            }
        }

        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
