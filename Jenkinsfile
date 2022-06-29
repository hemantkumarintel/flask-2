pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {
    stage('build') {
      steps {
//         sh 'pip3 install --upgrade pip'
//         sh 'pip3 install -r requirements.txt'
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
