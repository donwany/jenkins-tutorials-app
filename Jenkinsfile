pipeline {
   agent any

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

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

    }
}