pipeline {
  agent any
  stages {
    stage ('Checkout') {
      steps {
        git branch:'master', url: 'https://github.com/rachwrong/testing.git'
      }
    }
  }
}