pipeline {
  agent any

  tools {
    sonarqube
  }
  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/QA-Instructor/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
        steps {        
          sh "sonarqube/bin/sonar-scanner"
        }
    }
  }
  //   stage('SonarQube Analysis') {
  //     def scannerHome = tool 'sonarqube';
  //     withSonarQubeEnv() {
  //       sh "${scannerHome}/bin/sonar-scanner"
  //   }
  // }
}
