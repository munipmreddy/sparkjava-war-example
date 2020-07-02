pipeline{
    agent any
    stages{
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh'''
                mvn sonar:sonar \
  -Dsonar.projectKey=demoproject \
  -Dsonar.host.url=http://18.218.188.210:9000 \
  -Dsonar.login=5937685ceb24117827bc6039b58b4a1c7ec6fe4c
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
