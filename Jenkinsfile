pipeline {
    agent {
         label 'tomcat-slave'
}
    stages {
        stage('Git checkout') {
           steps {
               echo 'This is git checkout stage'
                                      git 'https://github.com/dileepunith6362/simple-java-project.git'
                  }
         }
        stage('Build stage') {
            steps {
                echo 'This is Build stage'
                             sh 'mvn clean install'     
            }
         } 
        stage('push to artifcatory stage') {
            steps {
                echo 'This is push stage'
                       sleep 15
            }
         } 
         stage('Deploy') {
            steps {
                echo 'This is deploy stage'
                              sh 'sudo cp /home/ec2-user/jenkins-slave1/workspace/jenkinsfilejob/target/*.war /opt/apache-tomcat-9.0.64/webapps/'
                  }
             }     
     }
}
