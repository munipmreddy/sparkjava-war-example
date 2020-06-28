pipeline{
    agent any
    stages{
        stage("code build"){
            agent{docker'maven:3-alpine'}
            steps{
                sh '''
                mvn sonar:sonar \
  -Dsonar.projectKey=project \
  -Dsonar.host.url=http://3.15.182.170:9000 \
  -Dsonar.login=72b7e2de27021107fcae8c56d74c90c0aedfdc2e
                '''
            }
        }
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh "mvn clean package"
            }
        }
    }
}
