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
                   print(data)
               }
           }
       }
   }
}
