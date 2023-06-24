pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('static analysis') {
      steps {
        sh '''./mvnw sonar:sonar \\
  -Dsonar.host.url=http://3.110.226.75:9000/ \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.token=sqp_71f935f7a1c001decff79fe48139efbb1a9cfa20'''
      }
    }

  }
}