pipeline {
	agent {
		label 'docker-server'
	}
	
	stages {
		stage('Build') {
			agent {
				docker {
					label 'docker-server'
					image 'maven:3.8.7-eclipse-temurin-11'
					args '-v /root/.m2:/root/.m2'
				}
			}
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
	}
}