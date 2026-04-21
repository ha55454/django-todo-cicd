pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh 'docker build -t todo .'
                sh 'docker stop todo-production || true'
                sh 'docker rm todo-production || true'
                sh 'docker run -d --name todo-production -p 8000:8000 todo'
            }
        }
    }
}
