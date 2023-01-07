pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        echo 'Jenkins Build Started'
        sh 'mvn clean compile'
      }
    }

  }
}