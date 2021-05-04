pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // 
                echo "Hello World"
            }
        }
        stage('Test') { 
            steps {
                // 
            }
        }
        stage('Deploy') { 
            steps {
                // 
            }
        }

        post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                   echo "Success"
                }
            }
    }
}