node {
    docker.image('node:lts-bullseye-slim').inside('-p 3000:3000') {
        stage('Checkout SCM') {
            checkout scm
        }
        stage('Build') {      
            sh 'npm install'     
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh' 
        }
    }
} 