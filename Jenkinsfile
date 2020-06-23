pipeline{
    agent any
    stages{
        stage("code quality"){
            agent{docker'maven:3-alpine'}
            steps{
                sh '''
                mvn sonar:sonar \
  -Dsonar.projectKey=corona \
  -Dsonar.host.url=http://18.217.181.146:9000 \
  -Dsonar.login=d04054ac4276e246a8777575a225b6157f5d6b47
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
