pipeline {
   agent any
   stages {
       stage('read') {
           steps {
               script {
                   def data = readFile(file: 'dev/prod.env')
                   println(data)
               }
           }
       }
   }
}
