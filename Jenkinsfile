pipeline {
    agent any
    tools {
        maven "maven"
      }
    stages {
        stage('Build') {
            steps {
                echo "Build"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy"
                sleep 3s
            }
        }
    }
    post {
        success {
            echo "success"
        }
        failure {
            echo "failure"
        }
        aborted {
            echo "aborted"
        }
    }
}
