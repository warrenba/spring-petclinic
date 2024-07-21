pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sleep 1
      }
    }

    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

  }
}