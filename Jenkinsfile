pipeline {
  agent { docker { image 'python:3-alpine' } }
  stages {
    stage('build') {
      steps {
        sh 'pip install flask'
        
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
