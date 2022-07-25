pipeline {
  agent any
  evironment{
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
