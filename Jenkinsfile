pipeline{
agent { label 'workstation' }
 stages{
 //no dependencies since it is static code.
  stage('code quality') {
   steps{
     sh 'sonar-scanner -Dsonar.host.url=http://172.31.39.191:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
     echo 'ok'
     }
   }
     //no unit test since it is static code.

   stage('deploy to production') {
    steps{
      echo 'CI'
      }
     }
 }
}


//annyalsis report will come from qualitygate

//here pipeline is failing yy beacuse in code it has some errror we cant do anything our job is just desghin pipeline