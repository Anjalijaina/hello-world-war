pipeline {
    agent none
    stages {
        stage('checkout') {
	agent {
	     label 'slavenode1'
            }
            steps {	
		    sh 'rm -rf hello-world-war'
		    sh 'git clone https://github.com/Anjalijaina/hello-world-war/'
            }
        }
	stage('Build') {
	  agent {
	     label 'slavenode1'
          }
            steps {		
	            sh 'mvn clean package'
            }
	}
	stage('Deploy') {
	   agent {
	     label 'slavenode2'
            }
            steps {		
	           // sh 'sudo cp $WORKSPACE/target/hello-world-war-1.0.0.war /var/lib/tomcat9/webapps'
            }
		
        }

    }
}
