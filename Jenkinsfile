pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn test'
      }
    }
    stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=calculator"
    }
  }
  }
}
