pipeline {
   agent any
   stages {

        stage("Git checkout"){
          steps {
           git credentialsId: 'github-cred', url: 'https://github.com/demodevops2/java-hello-world-webapp.git'
    }
        }
          
           stage("java build stage"){
              steps {
               sh 'mvn clean package'
               sh "mv target/*.war target/myweb.war"  
              }
           }
      
      stage("warfile deploy"){
         steps {
          sshagent(['slave id']) {
          sh "scp -o StrictHostKeyChecking=no target/myweb.war ubuntu@172.31.17.226:/var/lib/tomcat8/webapps"
}
         
         }
      
      
      }
           





}

}

