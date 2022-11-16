pipeline {
agent any
stages {
    stage('Build') {
        steps {
            sh 'python app.py'
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
