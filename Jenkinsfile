pipeline {
  agent { docker { image 'ubuntu:latest' } }
  stages {
    stage('build') {
      steps {
        sh 'sudo apt install python3-pip'
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
