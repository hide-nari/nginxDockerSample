pipeline {
    agent any

    stages {
        stage('one') {
            steps {
                echo 'docker build'
                sh 'docker buildx build -t test-nginx:v1 .'
            }
        }
        stage('two') {
            steps {
                echo 'container start'
                sh 'docker container run -d --rm --name nginx -p 8081:80 test-nginx:v1'
            }
        }
        stage('three') {
            steps {
                echo 'container stop'
                sh 'docker container stop nginx'
            }
        }
        stage('four') {
            steps {
                echo 'images docker ls'
                sh 'docker images'
                sh 'docker container ls'
            }
        }
    }
}