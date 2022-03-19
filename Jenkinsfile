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
        sh 'docker stop client && docker rm client'
        sh '''docker run -d -p 80:3000 \\
-e NEXT_PUBLIC_BASE_URL=\'https://daba-api.herokuapp.com/graphql\' \\
-e NODE_ENV=\'production\' \\
--name client daba-client'''
      }
    }

  }
}