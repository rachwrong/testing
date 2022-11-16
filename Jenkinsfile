pipeline {
agent any
stages {
	stage('Test') {
		steps {
            git branch:'main',url:'https://github.com/rachwrong/testing.git'
        }
    }

    stage('OWASP Check') {
      steps {
        dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
      }
    }
  }
post {
    always {
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
    }
    }
}
