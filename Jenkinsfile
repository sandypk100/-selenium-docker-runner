pipeline {
    // master executor should be set to 0
    agent any
    stages {
        stage('Start Grid') {
            steps {
                //sh
                bat "docker-compose up --scale node-docker=4 -d"
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
