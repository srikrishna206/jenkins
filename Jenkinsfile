pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/srikrishna206/jenkins.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-python-app')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image('my-python-app').run('-d -p 5000:5000')
                }
            }
        }
    }
}
