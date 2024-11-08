pipeline {
  agent any

  tools {
    nodejs 'Node' // Ім'я NodeJS установки, яке ви налаштували у Jenkins
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/SerhiiQAA/NewmanAPI_Test.git'
      }
    }

    stage('Install Newman and Reporter') {
      steps {
        sh 'npm install -g newman newman-reporter-htmlextra'
      }
    }

    stage('Run API Tests') {
      steps {
        sh 'newman run "Performance Testing.postman_collection.json" -r htmlextra --reporter-htmlextra-export newman/Performance_Testing_Report.html --reporter-htmlextra-title "Performance Testing Report"'
      }
    }

    stage('Archive Reports') {
      steps {
        archiveArtifacts artifacts: 'newman/Performance_Testing_Report.html', allowEmptyArchive: true
      }
    }
  }
}
