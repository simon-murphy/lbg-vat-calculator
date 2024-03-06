pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repositories
          git branch: 'main', url: 'https://github.com/simon-murphy/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonar-qube-1') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}