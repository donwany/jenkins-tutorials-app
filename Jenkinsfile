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
            agent {
                docker {
                    image 'gradle:6.7-jdk11'
                    // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh 'gradle --version'
            }
        }

        stage('Back-end') {
            agent {
                docker { image 'maven:3.8.1-adoptopenjdk-11' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }



    }
}