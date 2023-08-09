pipeline {
    agent any
 
    stages {
            stage('build') {
            steps {
                sh 'pwd'
                sh 'ls -l'
                sh 'mvn clean package deploy'
                  }
            }

            stage('SonarQube analysis') {
            environment {
              scannerHome = tool 'sonar-scanner';
              }
              
              steps {
           withSonarQubeEnv('sonar-server')
              sh "${scannerHome}/bin/sonar-scanner"
               }
               }
  }
}
 |
