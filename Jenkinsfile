pipeline {
  agent any
  
  environment {
    DOCKER_COMPOSE_FILE = 'Docker-compose.yml' // Update with file name
    CONTAINER_NAME = 'docker-mongo-express-1' // Update with your container name
    COMPOSE_DIR = '/home/yusuf/Desktop/Docker' // Update with the path to your docker-compose directory
    }
    
  stages {
    stage('Check and Start Docker Container ') {
      steps {

          sh '''#!/bin/bash

                    # Check if the container is running
                    cd ${COMPOSE_DIR}
                    if [ "$(docker ps --filter "name=${CONTAINER_NAME}" --filter "status=running" -q)" ]; then
                        echo "Express container is already running."
                    else
                        echo "Express container is not running. Starting it up..."
                        docker compose -f ${DOCKER_COMPOSE_FILE} up -d
                    fi'''

        echo 'Build Completed'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy Completed'
      }
    }

  }
}
