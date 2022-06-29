pipeline {
  agent { docker { image 'python:2-alpine' } }
  stages {
    stage('build') {
      steps {
        sh 'pip install --upgrade pip'
        sh 'pip install -r requirements.txt'
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
