pipeline {
    // master executor should be set to 0
    agent any
    stages {
        
        stage('pull latest image') {
	        steps {
		        bat "docker pull sandocker100/springboot:latest"
	    }
	}
        stage('Start Grid') {
            steps {
                //sh
                bat "docker-compose up -d selenium-hub node-docker"
            }
        }
        
        stage('Run tests') {
            steps {
                //sh
                bat "docker-compose up google-module"
            }
        }
        stage('Bring Grid Down') {
            steps {
                //sh
                bat "docker-compose down"
            }
        }
    }
}
