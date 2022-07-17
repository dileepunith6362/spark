pipeline {
        agent {
               label 'tomcat-slave'
}
           stages { 
               stage('git checkout') {
                   steps {
                   git branch: 'main', url: 'https://github.com/dileepunith6362/spark.git'
                }
            }
               stage('build') {
                   steps {
                   sh 'mvn clean install'
                }   
            }

             stage('push to artifactory') {
              steps {
               sleep 10
            }
        }

           stage('deploy') {
               steps {
                sh 'sudo cp /home/ec2-user/slavews/workspace/pipeline2/target/*.war /opt/apache-tomcat-9.0.64/webapps/'
            }
        }

}
}
