//DECLARATIVE PIPELINE SYNTAX
pipeline {
	//agent any
	agent any
	stages {
		stage('Build') {
			steps {
				sh '''
					# Create a local copy of the truststore
					mkdir -p /tmp/certs
					cp zscalar-rootca.crt /tmp/certs/
					cp $JAVA_HOME/lib/security/cacerts /tmp/certs/truststore.jks
					
					# Import certificate to local truststore
					keytool -importcert -file /tmp/certs/zscalar-rootca.crt -alias zscalar-root -keystore /tmp/certs/truststore.jks -storepass changeit -noprompt
					
					# Set JAVA_OPTS to use our custom truststore
					export JAVA_OPTS="-Djavax.net.ssl.trustStore=/tmp/certs/truststore.jks -Djavax.net.ssl.trustStorePassword=changeit"
				'''
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
