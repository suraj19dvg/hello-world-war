pipeline {
  agent any
    stages {
      stage ('build') {
        steps {
          sh 'mvn package'
          sh 'ls'
          }
        }
       stage ('deploy') {
        steps {
          sh 'sudo cp -R target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps/'
          sh 'sudo sh /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
          sh 'sleep 3'
          sh 'sudo sh /opt/apache-tomcat-10.0.27/bin/startup.sh'
        }
      }
   }
}
