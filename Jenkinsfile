node {

stage ('scm checkout') {
git url: 'https://github.com/chaitanyapratap19/maven-project.git', branch: 'mynewbranchscripted'
}

parallel creatapackage: {
stage('maven package goal') {
sh 'mvn package'
}
}, installm2mavenrepo: {

  stage('install maven goal')

{ sh 'mvn install'
}
  },
  failFast: true
}
