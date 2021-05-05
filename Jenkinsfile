// pipeline {
//    agent any

//    triggers{ cron('H/1 * * * *') }

//     stages {
//         stage('Stage 1') {
//             steps {
//                 echo 'Hello world!' 
//                 sh 'date'
//             }
//         }

//          stage('Stage 2') {
//             steps {
//                 echo 'Hello world! 2x' 
//                 sh 'date'
//             }
//         }

//         stage('Build') {
//             steps {
//                 echo 'Building..'
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo 'Testing..'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }

//     }
// }


pipeline {
    agent any

    tools {
        maven "mvn-install"
        //docker "docker-install"
    }

    stages {
        stage('Example') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
                sh "mvn --version"
                //sh "docker --version"
            }
        }
    }
}