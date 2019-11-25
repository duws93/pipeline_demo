pipeline {
   agent { label 'duws-3' }
   
   stages {
      
      stage('Prepare'){
         steps{
            sh 'git --version'
         }
      }
      
      stage('source'){
         steps{
            git branch : 'master' , url: 'https://github.com/duws93/git_home.git'
         }
      }
      
      stage('build'){
         steps{
            sh 'docker build -t ubuntu Dockerfile'
         }
      }      
   }
}
