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
  }
  environment {
    start_date = '20170513'
  }
}