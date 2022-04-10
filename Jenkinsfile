pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw package
cp -r ./target ~/target'''
      }
    }
    stage('Sonarqube Analysis') {
      steps {
        withSonarQubeEnv('static') {
          sh './mvnw clean package sonar:sonar'
        }
      }
    }
  }
}
