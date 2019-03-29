pipeline{
	agent any
	environment {
		ANYPOINT = credentials('ANYPOINT')		
	}
	stages{
		stage('BUILD'){
			steps {
				
					bat 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
				
			}
		}
		stage('DEPLOY'){
			steps{
				
					bat 'mvn -f mule-jenkins-pipeline/pom.xml clean package deploy -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Sandbox -DmuleDeploy'			
				
			}
		}
	}		
}