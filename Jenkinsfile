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
  -Dsonar.host.url=http://13.232.168.189:9000 \\
  -Dsonar.token=sqp_ec4d52db876219f03e111f893cb2312376eb4a92'''
      }
    }

  }
}