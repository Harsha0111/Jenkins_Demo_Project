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
    stage('Build') {
       steps {
         sh 'mvn -B -DskipTests clean package'
       }
    }
  }
}