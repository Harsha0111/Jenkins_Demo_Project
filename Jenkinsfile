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
            }
        }
    }
    post {
        success {
            mail body: 'Success', subject: 'Java Maven Project', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
        }
        failure {
            echo "failure"
        }
        aborted {
            echo "aborted"
        }
    }
}
