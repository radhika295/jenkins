pipeline {
    agent {

        node {
            label 'agent-1'
        }
    }
    stages {
        stage('Build'){
            steps {
                echo "Building"
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
            }
        }
        stage('Deploy'){
            steps {
                echo "Deploying"
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