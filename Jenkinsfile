pipeline {
  agent any

  tools {
    maven 'Maven_3_8_4'
  }

  stages {
    stage('Compile and Sonar Analysis') {
      steps {
        checkout scm
        sh '''
          mvn clean verify sonar:sonar \
          -Dsonar.projectKey=asgbuggywebapp \
          -Dsonar.organization=asgbuggywebapp \
          -Dsonar.host.url=https://sonarcloud.io \
          -Dsonar.token=2c83fef859a3c7f5b26bf9b64b7195cac9322e60
        '''
      }
    }
  }
}
