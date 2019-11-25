pipeline {
   agent { label 'duws-3' }
   
   stages {
      
      stage('Prepare'){
         steps{
            v = `git --version`
            echo "duws version is " $v
         }
      }
      
      stage('source'){
         steps{
            git branch : 'master' , url: 'https://github.com/duws93/git_home.git'
         }
      }
      
      stage('build'){
         steps{
            docker build .
         }
      }
      
   }
}
