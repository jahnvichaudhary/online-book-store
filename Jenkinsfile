pipeline {
  agent any
  stages {
    stage('Git_clone') {
      steps {
        git(url: 'https://github.com/jayaprakashdeav/onlinebookstore.git', branch: 'J2EE')
      }
    }

    stage('Build') {
      steps {
        sh '''echo "clone done"
export JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"
echo $JAVA_HOME
/usr/bin/mvn clean package
pwd
whoami
###########################################################
sudo service tomcat9 stop
sudo cp target/*.war /var/lib/tomcat9/webapps/
sudo service tomcat9 start
#scp target/*.war devops@184.72.71.18:/var/lib/tomcat9/webapps/drop/
###########################################################'''
      }
    }

  }
}