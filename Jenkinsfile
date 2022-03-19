pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Y" | docker system prune -a'
        sh 'docker build -t daba-client .'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker rm client'
        sh 'docker run -d -P --name client daba-client'
      }
    }

  }
}