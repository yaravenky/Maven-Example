pipeline
{

	agent any
	
		stages {
				stage ('scm checkout') {
					steps {
						git 'https://github.com/chaitanyapratap19/maven-project.git'
					}
				}



				stage ('code test') {
				       steps {
						withMaven(maven: 'MAVEN_HOME') {
							sh 'mvn test'
						}
				       }	       
				}
				       
	        }				       

	
}
