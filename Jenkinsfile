pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage(' Static Analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.host.url=http://172.31.88.25:9000 \\
  -Dsonar.login=sqp_d2f2dfa5546df4c204db53d1497416fa0cdd4989'''
      }
    }

  }
}