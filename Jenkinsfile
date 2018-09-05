pipeline {
	agent any
	stages{
		stage('build'){
			steps{
				sh 'mvn clean package'
				sh 'docker build -t tomcatwebapp:$BUILD_NUMBER .'
				sh 'docker run -p 6060:8080 -d --name=test_tomcat tomcatwebapp:$BUILD_NUMBER'
			}
		}
	}
}