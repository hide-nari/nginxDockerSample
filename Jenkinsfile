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
                echo 'docker run'
                sh 'docker container run -p 8081:80 test-nginx:v1'
            }
        }
        stage('three') {
            steps {
                echo 'three'
            }
        }
    }
}