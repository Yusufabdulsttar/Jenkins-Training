pipeline {
  agent any
  stages {
    stage('Build ') {
      steps {
          dir(path: '/home/yusuf/Desktop/Docker') {
              script {
                  // Check if the container is running
                  def containerRunning = sh(script: 'docker ps --filter "name=mongo-express" --filter "status=running" -q', returnStatus: true)

                  if (containerRunning == 0) {
                      echo "Mongo Express container is already running."
                  } else {
                      echo "Mongo Express container is not running. Starting it up..."
                      sh 'docker-compose -f Docker-compose.yml up -d'
                  }
              }
        }

        echo 'Build Completed'
      }
    }
  }
}
