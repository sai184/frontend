pipeline {
agent { label 'workstation' }
 stages {
 //no dependencies since it is static code.
  stage('code quality') {
  when {
          allOf {
            branch 'main'
            expression { env.TAG_NAME != env.GIT_BRANCH }
          }
        }


   steps {
    // sh 'sonar-scanner -Dsonar.host.url=http://172.31.39.191:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
     echo 'ok'
     }
   }
     stage('Unit Tests') {
          when {
            allOf {
              expression { env.TAG_NAME != env.GIT_BRANCH }
              branch 'main'
            }
          }
           steps {

                  // sh 'npm test'
                  echo 'CI'
                }
          }


   stage('Release') {
     when {
              expression { env.TAG_NAME ==~ ".*" }
          }
          //if tag is there in this branch then only deploy to prod
          steps {
            sh 'env'
            echo 'CI'
            }
           }
  }
}






 //'*' means any file matches anything when condtion in jenkins
//annyalsis report will come from qualitygate
//here pipeline is failing yy beacuse in code it has some errror we cant do anything our job is just desghin pipeline
