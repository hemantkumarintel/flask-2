pipeline {
  agent { docker { image 'python:3.9.4' } }
  stages {
    stage('build') {
      steps {
        sh '/usr/local/bin/python -m pip install --upgrade pip'
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
