pipeline {
  agent any
  environment{
    PATH = "/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.8.6/bin:$PATH"
  }

  stages{
     stage('Git checkout'){
      steps{
       git credentialsId: '2f4bdfb7-299a-44ec-8040-c5d848fff381', url: 'https://github.com/jgc-ckt-alr/maven-web-application-1.git'
      }
     }
    stage('maven build'){
      steps{
        sh "mvn clean package"
        sh "mv target/*.war target/myweb.war"
      }
    }
    stage ('deploy'){
      steps{
      
        sshagent(['Tomcat']) {
  

         sh """
              scp  -o StrictHostKeyChecking=no target/myweb.war ec2-user@172.31.44.140:/opt/tomcat-9.0.65/webapps/
              ssh ec2-user@172.31.44.140/opt/tomcat-9.0.65/bin/shutdown.sh
              ssh ec2-user@172.31.44.140/opt/tomcat-9.0.65/bin/startup.sh
              
         
         """
      }
       
      }
    }
    
    stage('build'){
      steps{
        echo "building the package"
      }
    }
   stage('Deploy') {
     steps{ 
        echo 'Deploying the package'
            }
  }
    stage('Test') {
      steps{
        echo 'Testing the project'
            }
     }
  }
}
