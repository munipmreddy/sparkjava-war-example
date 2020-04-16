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
            agent { docker 'maven:3-alpine' }
            steps {
            sh'''
mvn sonar:sonar \
  -Dsonar.projectKey=myproject1 \
  -Dsonar.host.url=http://3.133.91.41:9000 \
  -Dsonar.login=49ac157fb5930d5de72df1c5dcb59ce8de471974
  '''
            }
        }
    }
}
