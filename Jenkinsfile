pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {	
		    sh 'rm -rf hello-world-war'
		    sh 'git clone https://github.com/Anjalijaina/hello-world-war/'
            }
        }
	stage('Build') {
            steps {		
	            sh 'mvn clean package'
            }
	}
	stage('Deploy') {
            steps {		
	            sh 'sudo cp /var/lib/jenkins/workspace/${JOB_NAME_${BRANCH}}/target/hello-world-war-1.0.0.war /var/lib/tomcat9/webapps'
            }
		
        }

    }
}
