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

    stage('Code Quality Check via SonarQube') {
      steps {
        script {
          def scannerHome = tool 'SonarQube'; //
            withSonarQubeEnv('SonarQube') { 
              sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=OWASP -Dsonar.sources=."
            }
        }
      }
    }
  }
post {
    always {
	dependencyCheckPublisher pattern: 'dependency-check-report.xml'
	recordIssues enabledForFailure: true, tool: sonarQube()
    }
    }
}
