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
                //sh: 'scp -r -i  /home/ec2-user/newjenkins.pem /var/lib/jenkins/workspace/Spoon-Knife_master/  ec2-user@ec2-18-218-52-131.us-east-2.compute.amazonaws.com:/home/ec2-user/iis/'
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
