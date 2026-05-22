pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    } 
    environment {
        COURSE = "Jenkins"
    }
    stages {
        stage('Build') { 
            steps {
                script {
                    sh """
                        echo "Building declarative + scripted"
                        echo "$COURSE"
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
        success {
            echo "I will run if success"
        }
        failure{
            echo "I will stop if failure"
        }
    }
}