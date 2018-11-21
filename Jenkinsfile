pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building from RT...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing from RT...'
      }
    }
    stage('Deliver for development') {
      when {
        branch 'development'
      }
      steps {
        echo 'deploy DEV from RT'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        echo 'Finish...'
      }
    }
    stage('Deploy for production') {
      when {
        branch 'production'
      }
      steps {
        echo 'deploy PROD from RT'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        echo 'Finish'
      }
    }
  }
  environment {
    CI = 'true'
  }
}