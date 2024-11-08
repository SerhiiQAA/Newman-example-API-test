pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/SerhiiQAA/NewmanAPI_Test.git'
      }
    }

    stage('Install Newman') {
      steps {
        sh 'npm install -g newman'
      }
    }

    stage('Run API Tests') {
      steps {
        sh 'newman run шляхи_до_колекції.json'
      }
    }
  }
}
