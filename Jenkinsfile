pipeline{
    agent any
    stages{
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh'''
                mvn sonar:sonar \
  -Dsonar.projectKey=muni \
  -Dsonar.host.url=http://13.58.142.177:9000 \
  -Dsonar.login=be62f91e1d8bbf24de2042649dd9a104c50c3b16
                '''
            }
        }
        stage("code build"){
            agent{docker'maven:3-alpine'}
            steps{
                sh "mvn clean package"
            }

        }
    }
}   
