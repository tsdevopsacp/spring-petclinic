pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        echo 'Jenkins Build Started'
        sh 'mvnw clean compile'
      }
    }

  }
}