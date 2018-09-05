pipeline {
	agent any
	stages{
		stage('build'){
			steps{
				sh 'mvn clean package'
				sh 'docker build -t tomcatwebapp:${env.BUILD_ID} .'
				sh 'docker stop tomcatwebapp'
				sh 'docker rm tomcatwebapp'
				sh 'docker run -p 6060:8080 -d --name tomcatwebapp tomcatwebapp:${env.BUILD_ID}'
			}
		}
	}
}