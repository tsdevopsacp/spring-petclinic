pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''./mvnw clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://52.66.230.5:9000 \\
  -Dsonar.login=sqp_68cffa2bb623e1c15430c7d865bf315dc0170477'''
      }
    }

  }
}