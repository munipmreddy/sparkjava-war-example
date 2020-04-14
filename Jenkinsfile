pipeline {
                                agent {label 'slave1'}
    stages {
        stage('deployment') {
            steps {
            sh'''
            id
            pwd
            cd /home/ubuntu/
            ls -lrt
            curl -u admin:Password@321 -O "http://13.58.55.112:8081/artifactory/project/sparkjava-hello-world-1.0.war"
            cp sparkjava-hello-world-1.0.war /opt/tomcat/webapps/
        
            '''
                }
            }
                }
        }
