pipeline {
    agent any
       	stages {
             stage('Git Checkout') {
                   steps {
                         git 'https://github.com/singh96jyoti/mvn_sonar.git'
		}	}
		
        	stage('Build') {
	            	steps {
		            	   withSonarQubeEnv('sonar') {
			            	sh '/opt/maven/bin/mvn clean install sonar:sonar -Dmaven.test.skip=true'
		            	}
		            	}}
		   	stage("Quality Gate") {
                    steps {
                      timeout(time: 1, unit: 'MINUTES') {
                       waitForQualityGate abortPipeline: true
              }}}
		            	
        	stage("Deploy") {
                    steps {
                        sh '/opt/maven/bin/mvn clean install -Dmaven.test.skip=true'
                      }}
	}
}
