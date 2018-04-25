pipeline {
    agent any
	stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
	    post ('Deploy'){
            	success {
                	echo 'Now Archiving...'
                	archiveArtifacts artifacts: '**/target/*.war'
            	}
            }
        }
	stage('Deploy to Staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}
