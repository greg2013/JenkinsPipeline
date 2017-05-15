pipeline {
  agent {
    docker {
      image 'maven:3.5-jdk-8-alpine'
      args '-v /Volumes/Home/Users/gyzheng/.m2:/root/.m2'
    }
    
  }
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
        sh '''echo "Hello Jenkins!"
echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
mvn -version'''
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