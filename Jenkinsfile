pipeline {
   agent any
   stages {
      stage ('test'){
             steps {
                script {
                   def data = readFile(file: 'dev/prod.env')
                   data.each { key , value->
                   //echo "Walked through key $key and value $value"
                      println "${key}:${value}"
}
                }
               
             }
             }
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
