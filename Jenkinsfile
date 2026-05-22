pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    } 
    environment {
        COURSE = "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') { 
            steps {
                script {
                    sh """
                        echo "Building declarative + scripted"
                        echo "$COURSE"
                      #  sleep 10
                    """
                }
            }
        }
        stage('Test') { 
            steps {
                script {
                    sh """
                        echo "Testing"
                    """
                }
            }
        }
        stage('Deploy') { 
            steps {
                script {
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }
    post{
        always{
            echo "I will always say Hello again!"
            cleanWs()
        }
        success{
            echo "I will run if success"
        }
        failure{
            echo "I will stop if failure"
        }
        aborted{
            echo "pipeline is aborted"
        }
    }
}