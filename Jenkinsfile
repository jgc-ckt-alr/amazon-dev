currentBuild.displayName="newapp-#"+currentBuild.number
pipeline {
  agent {
    label 'my_new_node'
  }
  environment{
    PATH = "/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.8.6/bin:$PATH"

  }

  stages{
     stage('Git checkout'){
      steps{
        git credentialsId: '6cae6c92-2cbd-40a7-bda7-2f025d112528', url: 'https://github.com/jgc-ckt-alr/maven-web-application-1.git'
      }
     }
    stage('maven build'){
      steps{
        sh "mvn clean package"
        
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
