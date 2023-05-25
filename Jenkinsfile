pipeline {
    agent any

    stages {
        stage('Pre-build clean-up') {
            steps {
             
              sh 'docker stop $(docker ps -q)'
              sh 'docker rm $(docker ps -aq)'
              sh 'docker rmi $(docker images -aq)'
              sh 'docker network rm duo-net'
             
            }
        }  
        stage('Build') {
            steps {
                sh 'docker network create duo-net'
                sh 'docker build -t duo-app:v2 .'
                sh 'docker run -d -p --network duo-net --name flask-app duo-app:v2'
                sh 'docker run -d -p 80:80 --mount type=bind,source=$(pwd)/nginx.conf,target=/etc/nginx/nginx.conf --network duo-net --name nginx nginx:alpine'
                sh 'docker images' //
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                docker container ls
                '''
            }
        }
        stage('Test') {
            steps {
                //
                sh 'curl localhost'
            }
        }
    }
}

