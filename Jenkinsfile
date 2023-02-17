pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'gcc -o main/prgm main/mycpp.cpp'
        sh 'make -C main'
        echo 'Build Stage Successful'
      }
    }
    stage('Test') {
      steps {
        sh 'main/hello_exec'
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