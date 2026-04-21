pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t todo:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                echo 'Removing old container if exists...'
                sh 'docker rm -f todo-production || true'

                echo 'Running new container...'
                sh '''
                docker run -d \
                --name todo-production \
                -p 8000:8000 \
                --restart always \
                todo:latest
                '''
            }
        }
    }
}
