pipeline {
agent any
tools {
    // docker credentials
    'org.jenkinsci.plugins.docker.commons.tools.DockerTool' 'default'
}
stages {
    stage('Build') {
        steps {
            sh 'pip install -r requirements.txt'
            sh 'docker compose build --pull'
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
