node {
    def app

    stage('Clone repo'){
        checkout scm
    }

    stage('Build image') {
        app = docker.build('armanot/x-app')
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push('latest')
        }
    }
}