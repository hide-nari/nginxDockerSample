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
        stage('five') {
            steps {
                echo 'AWS login'
                sh 'aws login'
            }
        }
        stage('six') {
            steps {
                echo 'AWS ECR PUSH'
                sh 'aws ecr get-login-password --region ap-northeast-1 | docker login --username AWS --password-stdin 166666630572.dkr.ecr.ap-northeast-1.amazonaws.com'
                sh 'docker build -t nginx-test .'
                sh 'docker tag nginx-test:latest 166666630572.dkr.ecr.ap-northeast-1.amazonaws.com/nginx-test:latest'
                sh 'docker push 166666630572.dkr.ecr.ap-northeast-1.amazonaws.com/nginx-test:latest'
            }
        }
        stage('seven') {
            steps {
                echo 'AWS ECS Create Service'
            }
        }
    }
}