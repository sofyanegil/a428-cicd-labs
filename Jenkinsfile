node {
    docker.image('node:lts-bullseye-slim').inside('-p 3000:3000') {
        stage('Build') { 
            checkout scm
            sh 'npm install'     
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh' 
        }
        stage('Manual Approval') {
            input message: 'Lanjut ke tahap Deploy?'
        }
        stage('Deploy') {           
            sh './jenkins/scripts/deliver.sh'
            sleep(time:1 , unit: 'MINUTES')
            sh './jenkins/scripts/kill.sh'           
        }
    }
} 