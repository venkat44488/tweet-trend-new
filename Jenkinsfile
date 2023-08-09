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
             def scannerHome = tool 'sonar-scanner';
              }
              withSonarQubeEnv('sonar-server')
              { 
              steps {
              // If you have configured more than one global server connection, you can specify its name
              sh "${scannerHome}/bin/sonar-scanner"
               }
               }
  }
}
 |
