pipeline {
    agent {

        node {
            label 'agent-1'
        }
    }
    environment {
        COURSE = "Jenkins"
    }
    stages {
        stage('Build'){
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $COURSE
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
   }
}