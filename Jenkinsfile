pipeline {
    agent any

    stages {
        stage('Fetch code') {
            steps {
               git branch: 'main', url: 'https://github.com/pankajbetewad/demo1.git'
            }
        }
        stage('install apache') {
            steps {
              sh 'sudo apt install apache2 -y'
            }
        }
        stage('deploy app') {
            steps {
              sh 'sudo cp -R * /var/www/html'
            }
        }
    }
}
