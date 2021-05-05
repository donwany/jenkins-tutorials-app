pipeline {
   agent any

   triggers{ cron('H/1 * * * *') }

   tools {
        maven 'apache-maven-3.0.1' 
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

        stage('MVN') {
            steps {
                sh 'mvn --version'
            }
        }


    }
}