pipeline {
    agent any    
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                //sh 'npm install'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
             // Permission to execute
                //sh "chmod +x -R /home/ec2-user/"

                // Call SH
                //sh "${env.WORKSPACE}/../${env.JOB_NAME}@script/script.sh"
                
                sh '/home/ec2-user/scripts/biuld.sh'
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
                echo "Finish DEV ..."
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
                echo "Finish PROD ..."
                //sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
