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
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://172.31.89.41:9000 \\
  -Dsonar.login=sqp_a68171e513d2783708a7bc96f28e46ae5aae6835'''
      }
    }

  }
}