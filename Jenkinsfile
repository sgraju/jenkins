pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        COURSE = "Jenkins AWS"
    }
    options {
        timeout(time : 15, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                         echo "Building"
                         echo $COURSE
                         sleep 15
                         env
                    """
                }
            }
        }
        stage('Test'){
            steps {
                script{
                    sh """
                        echo "Testing"
                   """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }
    post {
         always{
            echo "I will always say Hello again!"
            cleanWs()
         }
         success {
            echo 'I will run if success'
         }
         failure {
            echo 'I will run if failure'
         }
         aborted {
            echo 'pipeline is aborted'
         }
    }
}