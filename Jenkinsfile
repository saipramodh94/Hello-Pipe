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
				bat 'mvn deploy -P cloudhub -Dmule.version=4.1.4 -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}'							
			}
		}
	}		
}