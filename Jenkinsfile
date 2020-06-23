pipeline{
  agent any
  stages{
    stage("code quality"){
      agent {docker'maven:3-alpine'}
      steps{
        sh '''
        mvn sonar:sonar \
  -Dsonar.projectKey=star \
  -Dsonar.host.url=http://18.188.149.66:9000 \
  -Dsonar.login=44861d8344181c308a107cda7709b041a6fe44b9
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
