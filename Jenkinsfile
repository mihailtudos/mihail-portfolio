pipeline {
    agent {
            label 'node && ubuntu'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'building the application'
                script {

                    docker.build('my-nuxt-app', '-f Dockerfile .')
                }
            }
        }
        stage('Testing the application') {
            steps {
                echo 'testing the application'
            }
        }
        stage('Run Docker Container') {
            steps {
                echo 'deploying the application'
                script {
                    docker.run('my-nuxt-app', '--name my-nuxt-container -p 3000:3000')
                }
            }
        }
    }
}
