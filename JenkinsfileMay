node{

	properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), 	pipelineTriggers([pollSCM('* * * * *')])])

echo "Job name is: ${env.JOB_NAME}"
echo "Build Number is: ${env.BUILD_NUMBER}"
echo "jenkins Home is: ${env.JENKINS_HOME}"

	def mavenHome = tool name: 'maven3.9.8'
	stage ('Checkoutcode'){
git branch: 'development', credentialsId: '25e83c6b-192e-4e27-8a30-46e3791ab724', url: 'https://github.com/may2024-Devops/maven-web-application.git'
}

stage('Build'){
	sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
	stage('UploadArtifactIntoNexus'){
	sh "${mavenHome}/bin/mvn clean deploy"
	}
	stage('DeployApplicationIntoTomcat'){
	sshagent(['33ccd6cc-4b47-4400-8a97-4374fab04363']) {
	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.232.60.226:/opt/apache-tomcat-9.0.90/webapps/"
	}
	}
         */
	}
