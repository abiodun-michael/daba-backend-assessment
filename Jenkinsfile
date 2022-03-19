pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Y" | docker system prune -a'
        sh 'docker build -t daba-client:${BUILD_NUMBER} .'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker stop client && docker rm client'
        sh 'docker run -d -p 80:3000 --name client daba-client'
      }
    }

  }
}