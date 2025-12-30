pipeline {
    agent {

        node {
            label 'agent-1'
        }
    }
    environment {
        COURSE = "Jenkins"
    }
    options {
        timeout(time:10,unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    //this is build section
    stages {
        stage('Build'){
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $COURSE
                       #sleep 10
                        env
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh """
                        echo "Building"
                    """
                }
            }
        }
        stage('Deploy'){
            // input {
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "alice,bob"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //      }
             when { 
                expression { "$params.DEPLOY" == "true" }
            }
             }
            steps {
                 script{
                    sh """
                        echo "Building"
                    """
                }
            }
        }
   }
   post {
        always{
            echo 'I will always say hello again'
            cleanWs()
        }
        success {
            echo 'I will always say hello again'
        }
        failure {
            echo 'I will always say hello again'
        }
        aborted {
            echo 'pipeline is timedout'
        }
   }
}