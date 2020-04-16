pipeline {
    agent any
    stages {
        stage('Example') {
         	agent { docker 'maven:3-alpine' } 
            	steps {
               		sh 'mvn compile'
            }
        }
    }
}
