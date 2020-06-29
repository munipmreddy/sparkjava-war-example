pipeline{
    agent any
    stages{
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh '''
                mvn sonar:sonar \
  -Dsonar.projectKey=red \
  -Dsonar.host.url=http://3.135.185.25:9000 \
  -Dsonar.login=3ddd2c83e57b6f0e2dae8589522125684f2a6de2
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
