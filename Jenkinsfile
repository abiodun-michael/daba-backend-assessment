pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''echo "Y" | docker service prune -a

docker build -t daba-client .'''
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker run -d -P --name client daba-client'
      }
    }

  }
}