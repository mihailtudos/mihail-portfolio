pipeline {
    agent {
        label 'node && ubuntu'
    }
    environment {
        DOCKER_IMAGE = 'my-nuxt-app'
        CONTAINER_NAME = 'my-nuxt-container'
        PORT_MAPPING = '3000:3000'
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE, '-f Dockerfile .')
                }
            }
        }
        stage('Stop and Remove Existing Container') {
            steps {
                script {
                    // Stop and remove the container if it exists
                    try {
                        docker.image(DOCKER_IMAGE).stop(CONTAINER_NAME)
                        docker.image(DOCKER_IMAGE).remove(CONTAINER_NAME)
                    } catch (Exception e) {
                        // Container does not exist or failed to remove
                        echo "No existing container to stop/remove"
                    }
                }
            }
        }
        stage('Run Docker Compose') {
            steps {
                script {
                    sh 'docker compose up -d'
                }
            }
        }
    }
}
