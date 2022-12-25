pipeline {
    agent any
    tools {
        maven "maven"
      }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                scdsc
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy"
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
