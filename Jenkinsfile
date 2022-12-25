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
            script {
                if(env.BRANCH_NAME == 'user') {
                   mail body: 'Success', subject: 'Maven Project - user', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } else if(env.BRANCH_NAME == 'maintainer') {
                   mail body: 'Success', subject: 'Maven Project - maintainer', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'   
                } else {
                   mail body: 'Success', subject: 'Maven Project - master', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } 
            }
        }
        failure {
             script {
                if(env.BRANCH_NAME == 'user') {
                   mail body: 'Failure', subject: 'Maven Project - user', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } else if(env.BRANCH_NAME == 'maintainer') {
                   mail body: 'Failure', subject: 'Maven Project - maintainer', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'   
                } else {
                   mail body: 'Failure', subject: 'Maven Project - master', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } 
            }
        }
        aborted {
            script {
                if(env.BRANCH_NAME == 'user') {
                   mail body: 'Aborted', subject: 'Maven Project - user', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } else if(env.BRANCH_NAME == 'maintainer') {
                   mail body: 'Aborted', subject: 'Maven Project - maintainer', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'   
                } else {
                   mail body: 'Aborted', subject: 'Maven Project - master', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                } 
            }
        }
    }
}
