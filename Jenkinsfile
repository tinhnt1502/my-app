pipeline {
    agent any
      stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/tinhnt1502/my-app.git'
            }
        }

          stage('Build') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub-1', url: 'https://index.docker.io') {
                    sh 'docker build -t my-app .'
                    sh 'docker push my-app'
                }
            }
        }
    
    }
}