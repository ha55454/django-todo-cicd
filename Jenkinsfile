pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh 'docker build -t todo .'
                sh 'docker stop todo-container || true'
                sh 'docker rm todo-container || true'
                sh 'docker run -d --name todo-container -p 8000:8000 todo'
            }
        }
    }
}
