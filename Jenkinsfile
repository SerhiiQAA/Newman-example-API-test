pipeline {
  agent any

  tools {
    nodejs 'Node' // Ім'я NodeJS установки, яке ви задали у налаштуваннях Jenkins
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/SerhiiQAA/NewmanAPI_Test.git'
      }
    }

    stage('Install Newman') {
      steps {
        sh 'npm install -g newman'
      }
    }

    stage('Run API Tests') {
      steps {
        sh 'newman run "Performance Testing.postman_collection.json"'
      }
    }
  }
}
