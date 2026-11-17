pipeline {
    agent any

    stages {
        stage('one') {
            steps {
                echo 'one'
                sh 'docker buildx build -t test-nginx:v1 .'
            }
        }
        stage('two') {
            steps {
                echo 'two'
            }
        }
        stage('three') {
            steps {
                echo 'three'
            }
        }
    }
}