pipeline
{

	agent any
	{

		stage ('scm checkout') {
		git 'https://github.com/chaitanyapratap19/maven-project.git'
		}



		stage ('code test) {
		       steps {
				withMaven(maven: 'MAVEN_HOME') {
					sh 'mvn test'
				}
		       }	       
		}

	}
}
