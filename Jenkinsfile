pipeline {
    agent any

    stages {
        stage('Clone repo') {

            steps {
                git url: 'https://github.com/MattTJX/QA-Exercise-1', branch: master
            }
        }
        stage('Pre-build clean-up') {
            steps {
              
              sh 'docker system prune -f'
              sh 'docker stop $(docker ps -q)'
              sh 'docker rm $(docker ps -aq)'
              sh 'docker rmi $(docker images -aq)'
             
            }
        }  
        stage('Build') {
            steps {
                sh 'docker build -t duo-app:v2'
                sh 'docker images' //
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

