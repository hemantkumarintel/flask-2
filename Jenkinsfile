pipeline {
  agent { docker { image 'python:latest' } }
  stages {
    stage('build') {
      steps {
        sh 'chown -R $USER /Users/$USER/Library/Caches/pip'
        sh 'pip install --user virtualenv'
        
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
