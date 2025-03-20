pipeline {
    agent any

    stages {
        stage('fetch code') {
            steps {
                git branch: 'main', url: 'https://github.com/pankajbetewad/devops-portfolio.git'
            }
        }
        stage('build docker image') {
            steps {
                sh 'docker build -t pankajbetewad3/devops-portfolio:${IMAGE_VERSION} .'
            }
        }
        stage('push image to dockerhub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'password', usernameVariable: 'userName')]) {
                    sh 'docker login -u ${userName} -p ${password}'
                    sh 'docker push pankajbetewad3/devops-portfolio:${IMAGE_VERSION}'
                }
                
            }
        }
    }
   
}
