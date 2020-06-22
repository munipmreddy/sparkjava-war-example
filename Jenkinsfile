pipeline{
  agent any
  stages{
    stage("code quality"){
      steps{
        sh '''
        mvn sonar:sonar \
  -Dsonar.projectKey=mytoken \
  -Dsonar.host.url=http://52.15.36.58:9000 \
  -Dsonar.login=mytoken
        '''
      }
    }
    stage("code build"){
      agent{docker'maven:3-alpine'}
        steps{
          sh 'mvn clean package'
        }
    }
  }
}
