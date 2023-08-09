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
            
              steps {
           withSonarQubeEnv('sonar-server')
              sh "sonar-scanner/bin/sonar-scanner"
               }
               }
  }
}
