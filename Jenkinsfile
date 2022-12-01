pipeline {
  agent any
    stages {
      stage ('build') {
        steps {
          sh 'mvn package'
          sh 'ls'
          }
        }
       stage ('my deploy') {
         agent any
         steps {
          sh 'cp -R target/hello-world-war-1.0.0.war /opt/tomcat/webapps'
          sh 'sh /opt/tomcat/bin/shutdown.sh'
          sh 'sleep 5'
          sh 'sh /opt/tomcat/bin/startup.sh'
        }
      }
   }
}
