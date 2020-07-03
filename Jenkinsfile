pipeline{
    agent any
    stages{
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh'''
                mvn sonar:sonar \
  -Dsonar.projectKey=yugi \
  -Dsonar.host.url=http://18.219.241.215:9000 \
  -Dsonar.login=53a5228aa6712ce68b49fa20d0faa725a473ee44
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
