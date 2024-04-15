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
        stage('Run Docker Container') {
            steps {
                script {
                    def dockerImage = docker.image(DOCKER_IMAGE)
                    def dockerContainer = dockerImage.run('--name ' + CONTAINER_NAME, '-p ' + PORT_MAPPING)
                }
            }
        }
    }
}
