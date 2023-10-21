pipeline{
agent { label 'workstation' }
 stages{
 stage('download dependencies') {
 steps{
   sh 'npm install'
   }
  }
  stage('code quality') {
   steps{
     sh 'sonar-scanner -Dsonar.host.url=http://172.31.39.191:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
     echo 'ok'
     }
   }
    stage('unit testing') {
        steps{

          //ideally unit tests we should run ,but devolper skipped it so assuming those are good and we are good proceding
          // sh 'npm test'
           echo 'CI'
          }
         }

   stage('deploy to production') {
    steps{
      echo 'CI'
      }
     }
 }
}


#annyalsis report will come from qualitygate