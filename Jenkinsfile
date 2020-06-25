pipeline {
    agent any
    stages {
        stage('build') {
         	agent { docker 'maven:3-alpine' } 
            	steps {
               		sh 'mvn clean package'
                    rtUpload (
    serverId: 'artifactory',
    spec: '''{
          "files": [
            {
              "pattern": "**/sparkjava-hello-world-1.0.war",
              "target": "project/"
            }
         ]
    }''',
 
    // Optional - Associate the uploaded files with the following custom build name and build number,
    // as build artifacts.
    // If not set, the files will be associated with the default build name and build number (i.e the
    // the Jenkins job name and number).
)
                }
                curl -uadmin:APASfQaa9ckVm7xtrFxAepxV1QE -O "http://3.133.91.41:8081/artifactory/project/sparkjava-hello-world-1.0.war"
scp sparkjava-hello-world-1.0.war ubuntu@18.218.123.220:/opt/tomcat/webapps/
            }
        }
    }
}
