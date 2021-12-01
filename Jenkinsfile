pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git url: 'https://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@github.com/Sadiq1106/JenkinsDependencyCheckTest'
			}
		}
 
		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}

