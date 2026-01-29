pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps { git 'https://github.com/you/devops-demo.git' }
    }

    stage('Build') {
      steps { sh 'docker build -t myapp .' }
    }

    stage('Push') {
      steps {
        sh 'docker login -u user -p pass'
        sh 'docker push myapp'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker run -d -p 80:80 myapp'
      }
    }
  }
}
