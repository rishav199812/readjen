pipeline {
   agent any
   environment {
      LAMBDA_NAME='ABCD'
      ENV='dev'
   }
   stages {
  
       stage('read') {
           steps {
               script {
                   def data = readFile(file: 'dev/prod.env')
                  def lineRemovedString = data.split('\n')
                  def evnVariables = lineRemovedString.join(',')
                   print(evnVariables)
                  echo String.format('aws lambda update-function-configuration --environment "Variables={%s}"', evnVariables)
         
               }
           }
       }
   }
}
