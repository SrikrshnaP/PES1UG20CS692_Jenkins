pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'gcc mycpp.cpp -o prgm'
        sh 'make -C main'
        echo 'Build Stage Successful'
      }
    }
    stage('Test') {
      steps {
        sh 'prgm'
        echo 'Test Stage Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline Failed'
    }
  }
}