pipeline {
  agent { docker { image 'python:3.9.4' } }
  stages {
    stage('build') {
      steps {
        sh 'virtualenv enviroment_name -p python3'
        sh 'source enviroment_name/bin/activate'
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
