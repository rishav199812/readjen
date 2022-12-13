pipeline {
   agent any
   stages {
       stage('read') {
           steps {
               script {
                   def data = readFile(file: 'dev/prod.env')
                  def lineRemovedString = data.split('\n')
                  def evnVariables = lineRemovedString.join(',')
                   print(evnVariables)
                  //echo String.format('aws lambda update-function-configuration --environment "Variables={%s}"', evnVariables)
         
               }
           }
       }
      stage('write'){
         steps {
            script {
               echo String.format('aws lambda update-function-configuration --environment "Variables={%s}"', '${evnVariables}')
            }
         }
      }
   }
}
