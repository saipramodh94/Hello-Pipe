pipeline{
	agent any
	environment {
		ANYPOINT = credentials('ANYPOINT')		
	}
	stages{
		stage('BUILD'){
			steps {				
				bat 'mvn -f pom.xml clean install'				
			}
		}
		stage('DEPLOY'){
			steps{				
				bat 'mvn -f pom.xml package deploy -P -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Sandbox -DmuleDeploy'							
			}
		}
	}		
}