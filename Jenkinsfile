pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/QA-Instructor/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
        steps {
          def scannerHome = tool 'sonarqube';
          withSonarQubeEnv() {
            sh "${scannerHome}/bin/sonar-scanner"
          }
        }
    }
}