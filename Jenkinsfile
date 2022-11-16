pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "building the repo"'
          }
        }
      }
    }

    stage('Deploy')
    {
      steps {
        echo "deploying the application"
      }
    }

  }
}
