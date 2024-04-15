pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-nuxt-app', '-f Dockerfile .')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.run('my-nuxt-app', '--name my-nuxt-container -p 3000:3000')
                }
            }
        }
    }
}
