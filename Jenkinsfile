pipeline {
    agent any
    stages {
      stage('Pre-build clean-up) {
            steps {
              
              docker stop $(docker ps -q)
              docker rm $(docker ps -aq)
              docker rmi $(docker images -aq)
             
            }
         }  
        stage('Build') {
            steps {
                docker build -t duo-app:v2
                docker images
            }
        }
        stage('Deploy') {
            steps {
                //
            }
        }
        stage('Test') {
            steps {
                //
            }
        }
    }
}
