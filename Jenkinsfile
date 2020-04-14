pipeline {
    agent any
    stages {
        stage('build') {
         	agent { docker 'maven:3-alpine' } 
            	steps {
               		sh 'mvn clean package'
            }
        }
        stage('sonarqube') {
            mvn sonar:sonar \
  -Dsonar.projectKey=myproject \
  -Dsonar.host.url=http://13.58.55.112:9000 \
  -Dsonar.login=d7cfbaf53687870f6fefb137ab38dfe72b05ec61
        }
    }
}
