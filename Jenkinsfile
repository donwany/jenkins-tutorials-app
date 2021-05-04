pipeline {
    agent {
        docker { image 'node:14-alpine' }
    } 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
                sh 'date'
            }
        }

         stage('Stage 2') {
            steps {
                echo 'Hello world! 2x' 
                sh 'date'
            }
        }

        stage('Stage 3') {
            steps {
                sh 'node --version'
            }
        }
    }
}