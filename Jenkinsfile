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
			
			     stage ('code package') {
				       steps {
						withMaven(maven: 'MAVEN_HOME') {
							sh 'mvn package'
						}
				       }	       
			      }
			
			
			    stage ('code install') {
				       steps {
						withMaven(maven: 'MAVEN_HOME') {
							sh 'mvn install'
						}
				       }	       
				}
				       
	        }				       

	
}
