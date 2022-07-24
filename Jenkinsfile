pipeline {
  agent any
  stages{
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
