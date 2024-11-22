pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
      }
    }

    stage('Maven Test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'm398'
  }
}