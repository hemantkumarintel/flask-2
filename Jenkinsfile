pipeline {
  agent { docker { image 'python:latest' } }
  stages {
    stage('build') {
      steps {
        sh 'pip3 install --upgrade pip --user'
        sh 'pip3 install -r requirements.txt'
        sh 'pip install itsdangerous==1.1.0 --user'
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
