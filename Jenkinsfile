pipeline {
    agent any
    stages {
        stage('build') {
         	agent { docker 'maven:3-alpine' } 
            	steps {
               		sh 'mvn clean package'
            }
        }
        stage('deployment') {
            agent any
            steps {
            sh'''
            cd /opt/tomcat/webapps
            ls -lrt
            curl -u admin:Password@321 -O "http://13.58.55.112:8081/artifactory/project/sparkjava-hello-world-1.0.war"
  '''
            }
        }
    }
}
