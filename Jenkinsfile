pipeline {
	agent any
	stages{
		stage('build'){
			steps{
				sh 'mvn clean package'
				sh 'docker build -t tomcatwebapp:$BUILD_NUMBER .'
				sh 'docker rm -f tomcatwebapp'
				sh 'docker run -p 6060:8080 -d --name tomcatwebapp tomcatwebapp:$BUILD_NUMBER'
			}
		}
	}
}