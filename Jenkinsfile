pipeline{
	agent any
	environment {
		ANYPOINT = credentials('ANYPOINT')		
	}
	stages{
		stage('BUILD'){
			steps {
				withMaven(maven:'maven'){
					bat 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
				}
			}
		}
		stage('DEPLOY'){
			steps{
				withMaven(maven:'maven'){
					bat 'mvn -f mule-jenkins-pipeline/pom.xml package deploy -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Sandbox -DmuleDeploy'			
				}
			}
		}
	}		
}