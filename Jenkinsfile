currentBuild.displayName="newapp-#"+currentBuild.number
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
        
      }
    }
    stage('sonarqube report'){
      steps{
      withSonarQubeEnv('sonarqube-server')
      { 
        sh "mvn sonar:sonar" 
      }
      }
    }
        stage ('deploy'){
      steps{
      
      deploy adapters: [tomcat9(credentialsId: '130dbd4a-406c-47f7-88c3-e1120451466a', path: '', url: 'http://43.205.96.50:8080/')], contextPath: '/philips', war: '**/*.war'
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
