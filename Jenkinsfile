pipeline {

agent any

stages
{

stage('cloning code')

{

steps

{git 'https://github.com/chaitanyapratap19/maven-project.git'
}
}

stage('compile my project')
{
steps
{
withMaven(jdk: 'localJDK', maven: 'localMaven') {
    sh 'mvn compile'
}}}
    
stage('test my project')
{
steps
{
withMaven(jdk: 'localJDK', maven: 'localMaven') {
    sh 'mvn test'
}}}

}
}
