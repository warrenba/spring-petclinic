pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
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

    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('test') {
      steps {
        sh './mvnw test'
      }
    }

  }
}