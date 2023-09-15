pipeline {
    agent any

    stages {
        stage('Build and Push Docker Image') {
            steps {
                script {
                    // Build and tag the Docker image
                    docker.build('diwakarrajanna/devops_guvi_geektask:latest')

                    // Push the Docker image to Docker Hub using Jenkins credentials
                    docker.withRegistry('https://registry.hub.docker.com', 'docker_hub') {
                        docker.image('diwakarrajanna/devops_guvi_geektask:latest').push()
                    }
                }
            }
        }
    }
    
    post {
        success {
            echo "Docker image built and pushed successfully."
        }
    }
}