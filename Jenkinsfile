pipeline{
  agent any
  stages{
    stage("code quality"){
      agent{docker'maven:3-alpine}
        steps{
          sh 
             '''        
          mvn sonar:sonar \
      -Dsonar.projectKey=mytoken \
      -Dsonar.host.url=http://52.15.36.58:9000 \
      -Dsonar.login=6748e7da670032ed8185502dfaddbb6ecaf22802
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
