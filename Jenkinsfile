pipeline {
    agent any
	stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
        	post ('Deploy'){
            	success {
                	echo 'Now Archiving...'
                	archiveArtifacts artifacts: '**/target/*.war'
            	}
            }
        }
    }
}