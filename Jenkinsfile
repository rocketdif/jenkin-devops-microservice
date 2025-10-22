//DECLARATIVE PIPELINE SYNTAX
pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} pose {
		always {
			echo "I'm awesome. I run always"
		}
		success {
			echo "I'm awesome. I run on success"
		}
		failure {
			echo "I'm awesome. I run on failure"
		}
	}
}
