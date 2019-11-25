pipeline {
   agent { label 'duws-3' }

   stages {
      stage('Hello') {
         steps {
            echo 'Hello World again'
         }
      }
   }
   post {
      always {
         echo " finish job"
      }
   }
}
