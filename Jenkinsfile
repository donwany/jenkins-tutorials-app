pipeline {
   agent { dockerfile true }

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

    stage('Test') {
                steps {
                    sh 'node --version'
                    sh 'svn --version'
                }
        }

    }
}