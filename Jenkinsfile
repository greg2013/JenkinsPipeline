pipeline {
  agent any
  stages {
    stage('Echo') {
      steps {
        echo 'Hello Jenkins Pipeline'
      }
    }
    stage('Checkout') {
      steps {
        git 'https://github.com/greg2013/spring-boot.git'
      }
    }
    stage('Build') {
      steps {
        sh 'echo "Hello Jenkins!"'
      }
    }
    stage('Test') {
      steps {
        junit(allowEmptyResults: true, testResults: 'Automation')
      }
    }
    stage('Deploy') {
      steps {
        echo 'All Done!'
      }
    }
  }
  environment {
    start_date = '20170513'
  }
}