pipeline {
	agent {
		docker {
			image 'maven:3.8.7-eclipse-temurin-11'
			args '-v /root/.m2:/root/.m2'
		}
	}
	stages {
		// Required to ensure our jenkins-docker tool (added as a global tool in Jenkins)
		// is available from the PATH
		stage('Initialize') {
	        def dockerHome = tool 'jenkins-docker'
	        env.PATH = "${dockerHome}/bin:${env.PATH}"
    	}
		stage('Build') {
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
	}
}