pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
      agent any
      steps {
        sh 'sh \'mvn test\''
      }
    }
    stage('Deliver') {
      steps {
        sh 'sh \'./jenkins/scripts/deliver.sh\''
      }
    }
  }
}