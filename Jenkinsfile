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
        sh 'mvn clean compile'
      }
    }

    stage('Static Analysis') {
      agent {
        node {
          label 'test'
        }

      }
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=spring-petclinic \\
  -Dsonar.host.url=http://15.206.184.5:9000 \\
  -Dsonar.login=sqp_76e6bba9ce90bb0d473c49223b8aa298682ef327'''
      }
    }

  }
}