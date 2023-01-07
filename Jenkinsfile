pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Jenkins Build Started'
        sh 'mvn clean compile'
      }
    }

  }
}