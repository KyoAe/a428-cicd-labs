node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Checkout SCM') {
            checkout([$class: 'GitSCM', branches: [[name: '*/react-app']], extensions: [], userRemoteConfigs: [[url: '/home/Downloads/a428-cicd-labs']]])
        }
        stage ('Build') {
            sh 'npm install'
        }
        stage ('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}