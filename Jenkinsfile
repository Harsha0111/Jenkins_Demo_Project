pipeline {
    agent any
    tools {
        maven "maven"
      }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                //sh 'mvn clean package -Dmaven.test.skip=true'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy"
                script {
                    sh 'cp /var/lib/jenkins/workspace/Java_Maven_Project_user/target/jenkins-0.0.1.war
 /var/lib/tomcat9/webapps'
                   if(env.BRANCH_NAME == 'maintainer') {
                        mail body: 'Approval Message for maintainer' + '\n' + "Please visit the console of the build ${BUILD_URL}input to approve or reject.", subject: 'Maven Project - maintainer', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                        try {
                          input message: 'Do you wanna deploy to maintainer?', ok: 'Yes',submitter: 'maintainer'
                        } catch (org.jenkinsci.plugins.workflow.steps.FlowInterruptedException e) {
                          currentBuild.result = 'ABORTED'
                        }
                   } else if(env.BRANCH_NAME == 'master') {
                        mail body: 'Approval Message for master' + '\n' + "Please visit the console of the build ${BUILD_URL}input to approve or reject.", subject: 'Maven Project - master', to: 'selviharsha@gmail.com', from: 'harshajsharsh@gmail.com'
                        try {
                          input message: 'Do you wanna deploy to master?', ok: 'Yes',submitter: 'Harsha'
                        } catch (org.jenkinsci.plugins.workflow.steps.FlowInterruptedException e) {
                          currentBuild.result = 'ABORTED'
                        }
                   }
                }
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
