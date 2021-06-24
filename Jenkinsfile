pipeline
{

	agent any
	
		stages {
				stage ('scm checkout') {
					steps {
						git 'https://github.com/yaravenky/Maven-Example/
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
			
			
			
			stage ('ssh tomcat') {
				       steps {
						sshPublisher(publishers: [sshPublisherDesc(configName: 'Tomcat', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/lib/tomcat/webapps', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
				       }	       
			}
			
			
			stage ('deploy to tomcat') {
				steps {
						sshagent (['52.15.99.183']) {
						sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@52.15.99.183:/var/lib/tomcat/webapps'
						}
				}
	
}
				       
	        	}				       

	
}
