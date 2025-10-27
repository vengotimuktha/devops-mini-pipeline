pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/vengotimuktha/devops-mini-pipeline.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        script {
          docker.build('gcp-demo:latest')
        }
      }
    }
    stage('Run Container') {
      steps {
        sh 'docker run -d -p 8081:80 gcp-demo:latest'
      }
    }
  }
}
