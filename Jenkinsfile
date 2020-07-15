pipeline {
   agent { label 'master' }
   
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
            sh ' cd $WORKSPACE'
            sh 'docker build -t ubuntu .'
         }
      }
   }
      post{
         success{
            emailext(
               subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
               body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
<p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>""",
               to: "wenshu.du@daocloud.io",
               from: "wenshu.du@daocloud.io"
            )
         }
         failure{
            emailext (
                subject: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """<p>FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
<p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>""",
                to: "wenshu.du@daocloud.io",
                from: "wenshu.du@daocloud.io"
            )   
         }
      }
}
