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
                sh 'docker container run -d --name nginx -p 8081:80 test-nginx:v1'
            }
        }
        stage('three') {
            steps {
                echo 'container stop'
                sh 'docker container stop nginx'
            }
        }
    }
}