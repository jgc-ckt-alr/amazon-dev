pipeline {
  agent any
  stages{
     stage('Git checkout'){
      steps{
        git branch: 'development', credentialsId: '2f4bdfb7-299a-44ec-8040-c5d848fff381', url: 'https://github.com/jgc-ckt-alr/maven-web-application-1.git'
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
