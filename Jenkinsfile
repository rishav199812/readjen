pipeline {
   agent any
   stages {
       stage('read') {
           steps {
               script {
                  echo "Removing .env files"
                        sh 'rm dev/*.dnv'
                   def data = readFile(file: 'dev/prod.env')
                  def lineRemovedString = data.split('\n')
                   evnVariables = lineRemovedString.join(',')
                  env = "dev"
                  func = "test"
                   print(evnVariables)
                  //echo String.format('aws lambda update-function-configuration --environment "Variables={%s}"', evnVariables)
         
               }
           }
       }
      stage('write'){
         steps {
            script {
               //echo "${evnVariables}"
               //echo String.format('aws lambda update-function-configuration --environment "Variables={${evnVariables}}" ')
               echo String.format('aws lambda update-function-configuration --function-name {%s}-{%s} --environment "Variables={%s}"', "${env}","${func}","${evnVariables}" )
            }
         }
      }
   }
}
