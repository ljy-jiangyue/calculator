pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Unit test'){
      steps {
	sh 'mvn test'
      }
    }
    stage('sonar Analysis'){
      steps {
        sh 'mvn clean verify sonar:sonar \
  -Dsonar.projectKey=calculator1 \
  -Dsonar.host.url=http://192.168.56.10:9000 \
  -Dsonar.login=44679babbf99a576709bb41b22957ee722555dcc' 
     }
    }

  }
}
