pipeline {
  agent {label "master"}
    stages {
      stages ("tomcat build") {
        steps {
          sh 'mvn package'
          sh 'ls'
          echo "packages build"
          }
        }
       stage ("tomcat deploy") {
        steps {
          sh 'sudo cp -R target/hello-world-war-1.0.0.war /opt/apache-tomcat-9.0.69/webapps/'
          sh 'sudo sh /opt/apache-tomcat-9.0.69/webapps/bin/shutdown.sh'
          sh 'sudo sleep 3'
          sh 'sudo sh /opt/apache-tomcat-9.0.69/bin/startup.sh'
          echo "deployment is successfull"
          echo "copy the public ip of instance and open it browser port:8080"
          }
        }
      }
    }
   }
