pipeline{
  agent any
  stages{
    stage("build"){
      agent{docker'maven:3-alpine'}       
        steps{
          sh "mvn clean package"
      }
    }
  }
}
