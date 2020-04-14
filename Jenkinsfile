pipeline {
    agent any
    stages {
        stage('deployment') {
                            agent {label ‘slave1’}
            steps {
            sh'''
            id
            pwd
            cd /home/ubuntu/
            ls -lrt
            cd /opt/tomcat/webapps
            curl -u admin:Password@321 -O "http://13.58.55.112:8081/artifactory/project/sparkjava-hello-world-1.0.war"
            '''
                }
            }
                }
        }
