pipeline {
  agent {
    node {
      label 'test'
    }

  }
  stages {
    stage('Compile') {
      steps {
        echo 'Jenkins Build Started'
        sh 'mvnw clean compile'
      }
    }

  }
}