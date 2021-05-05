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


    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'VERSION', choices: ['1.1.0', '1.1.1', '1.1.2'], description: 'Version to build')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    tools {
        maven "mvn-install"
        //docker "docker-install"
    }

    stages {
        stage('Example') {
            // input {
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "alice,bob"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //     }
            // }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
                sh "mvn --version"
                //sh "docker --version"
            }
        }

        stage('Example Test') {
            agent { docker 'openjdk:8-jre' } 
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }

        stage('Parameters') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }

        // post { 
        //     always { 
        //         echo 'I will always say Hello again!'
        //     }
        //     success {
        //         echo "Success"
        //     }
        // }
    }
}