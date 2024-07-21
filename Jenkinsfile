pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sleep 1
        sh './mvnw compile'
      }
    }

    stage('static analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.projectName=\'Petclinic\' \\
  -Dsonar.host.url=http://13.235.84.230:9000 \\
  -Dsonar.token=sqp_80b7ab81534b2715c1abef47b2b4e0b53e4b944a'''
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw "-Dtest=**/petclinic/*/*.java" test'
      }
    }

    stage('Package') {
      steps {
        sh './mvnw package -DskipTests=true'
      }
    }

  }
}