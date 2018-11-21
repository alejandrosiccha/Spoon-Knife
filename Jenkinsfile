pipeline {
    agent any    
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                //sh 'npm install'
                echo "Building from RT..."
            }
        }
        stage('Test') {
            steps {
                //sh './jenkins/scripts/test.sh'
                echo "Testing from RT..."
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development' 
            }
            steps {
                //sh './jenkins/scripts/deliver-for-development.sh'
                echo "deploy DEV from RT"
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                //sh './jenkins/scripts/kill.sh'
                echo "Finish..."
            }
        }
        stage('Deploy for production') {
            when {
                branch 'production'  
            }
            steps {
                //sh './jenkins/scripts/deploy-for-production.sh'
                echo "deploy PROD from RT"
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                echo "Finish"
                //sh './jenkins/scripts/kill.sh'
            }
        }
    }
}