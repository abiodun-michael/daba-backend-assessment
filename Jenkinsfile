pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t daba-client .'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker run -P daba-client'
      }
    }

  }
}