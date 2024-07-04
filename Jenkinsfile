pipeline {
  agent any
  stages {
    stage('Build ') {
      steps {
        sh '''#!/bin/bash

                    # Check if the container is running
                    if [ "$(docker ps --filter "name=mongo-express" --filter "status=running" -q)" ]; then
                        echo "Express container is already running."
                    else
                        echo "Express container is not running. Starting it up..."
                        docker compose -f Docker-compose.yml up -d
                    fi'''
        echo 'Build Completed'
      }
    }

    stage('Final Test') {
      steps {
        echo 'Test Completed'
      }
    }

    stage('Test') {
      steps {
        echo 'Test Completed'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy Completed'
      }
    }

  }
}