pipeline {
  agent any
  stages {
    stage('Start') {
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
        parallel(
          "Test": {
            junit(allowEmptyResults: true, testResults: 'Automation')
            
          },
          "Automation": {
            echo 'Automated tests passed!'
            
          },
          "Acceptance": {
            echo 'Acceptance tests passed!'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        parallel(
          "Deploy": {
            echo 'All Done!'
            
          },
          "Smoking Test": {
            echo 'Signed'
            
          }
        )
      }
    }
    stage('End') {
      steps {
        pwd()
      }
    }
  }
  environment {
    start_date = '20170513'
  }
}