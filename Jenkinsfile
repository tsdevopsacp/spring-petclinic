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
        sh '''./mvnw sonar:sonar \\
-Dsonar.host.url=http://172.31.2.90:9000/ \\
-Dsonar.projectKey=PetClinic_MavenProject1 \\
-Dsonar.login=sqp_2e46ef936200aad05b45354b78d7d7d914a22c30'''
      }
    }

  }
}