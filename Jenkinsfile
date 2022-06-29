pipeline {
  agent { docker { image 'python:latest' } }
  stages {
    stage('build') {
      steps {
        sh 'sleep 10'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
