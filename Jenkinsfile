pipeline {
    agent any
    stages {
      stage('Pre-build clean-up) {
            steps {
              
              docker stop $(docker ps -q)
              docker rm $(docker ps -aq)
              docker rmi $(docker images -aq)
              
              
        stage('Build') {
            steps {
                // 
            }
        }
        stage('Test') {
            steps {
                //
            }
        }
        stage('Deploy') {
            steps {
                //
            }
        }
    }
}
