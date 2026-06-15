pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without docker"
                    ls -ltra
                    touch container_off.txt
                    ls -ltra
                '''
            }
        }

        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Without docker"
                    ls -ltra
                    touch container_on.txt
                    ls -ltra
                '''
            }
        }
    }
}