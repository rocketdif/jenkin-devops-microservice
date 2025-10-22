//DECLARATIVE PIPELINE SYNTAX
pipeline {
	//agent any
	agent any
	stages {
		stage('Build') {
			steps {
				bat 'keytool -importcert -file zscalar-rootca.crt -alias zscalar-root -keystore "%JAVA_HOME%/lib/security/cacerts" -storepass changeit -noprompt'
				echo "Build"
				echo "BUILD PATH: $PATH"
				echo "BUILD NUMBER: ${env.BUILD_NUMBER}"
				echo "BUILD ID: ${env.BUILD_ID}"
				echo "JOB NAME: ${env.JOB_NAME}"
				echo "BUILD TAG: ${env.BUILD_TAG}"
				echo "BUILD URL: ${env.BUILD_URL}"
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
	}

	post {
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
