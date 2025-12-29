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
    stages {
        stage('Build'){
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $COURSE
                       #sleep 10
                        env
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