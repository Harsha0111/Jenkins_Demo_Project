pipeline {
  agent any
  tools {
    maven "maven"
  }
  stages {
    stage('Automatic trigger') {
      steps {
        echo "Hello World"
      }
    }
    stage('Build code') {
      steps {
        sh "mvn clean install"
      }
    }
  }
}