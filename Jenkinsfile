pipeline {
    agent any

    stages {
        stage('Create Docker image') {
            steps {
                sh 'docker build -t blog:v1 .'
            }
        }
        stage('Deleting old container') {
            steps {
                sh 'docker rm -f blog'
            }
        } 
        stage('Create a container') {
            steps {
                sh 'docker run -d --name blog -p 90:80 blog:v1'
            }
        }
        stage('Dangling Image remove') {
            steps {
                sh 'docker image prune -f'
            }
        }

        
    }
}
