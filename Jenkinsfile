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
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=PetClinic_MavenProject1 \\
  -Dsonar.projectName=\'PetClinic_MavenProject1\' \\
  -Dsonar.host.url=172.31.2.90:9000 \\
  -Dsonar.token=sqp_2e46ef936200aad05b45354b78d7d7d914a22c30
'''
      }
    }

  }
}