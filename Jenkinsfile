pipeline {
	agent any
	tools {
	 maven 'maven1'
	       }
	agent {
	 label 'master'
	      }
	stages {
	                stage ('build') {
			steps {
				sh 'mvn clean install -DskipTests'
			}
		
		}
		stage ('test') {
			steps {
				sh 'mvn test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.*xml'
				}
			}
		}
	}
}

