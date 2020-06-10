pipeline {
    agent any
       	stages {
             stage('Git Checkout') {
                   steps {
                         git 'https://github.com/singh96jyoti/mvn_sonar.git'
		}	}
		
        	stage('Build') {
	            	steps {
		            	  
			            	sh '/opt/maven/bin/mvn clean install -Dmaven.test.skip=true'
		            	
		            	}}
		   			            	
        	stage("Deploy") {
                    steps {
                        sh '/opt/maven/bin/mvn clean deploy -Dmaven.test.skip=true'
                      }}
	}
}
