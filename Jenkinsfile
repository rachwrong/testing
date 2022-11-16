pipeline {
  agent any
  stages {
    stage('Build') {
        steps {
            sh 'docker compose build --pull"'
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

