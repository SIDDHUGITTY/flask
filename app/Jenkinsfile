pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/SIDDHUGITTY/flask.git'
            }
        }
        stage('BUILD & RUN') {
            steps {
                sh '''cd app
                sudo chmod 777 /var/run/docker.sock
                docker compose -f compose.yaml up -d
                '''
            }
        }
    }
}
