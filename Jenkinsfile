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
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deliver') {
      steps {
        sh 'sh \'./jenkins/scripts/deliver.sh\''
      }
    }
  }
}