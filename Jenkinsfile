pipeline {
  agent {
    node {
      label 'test'
    }

  }
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

    stage('Unit test') {
      steps {
        sh './mvnw "-Dtest=**/petclinic/*/*.java" test'
      }
    }

    stage('package') {
      steps {
        sh './mvnw package -DskipTests=true'
      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            sh './mvnw spring-boot:run </dev/null &>/dev/null &'
          }
        }

        stage('Integration and performance') {
          steps {
            sh './mvnw verify'
          }
        }

      }
    }

  }
}