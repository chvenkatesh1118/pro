pipeline {
   agent {
     label 'server1'
   }
  stages {
     stage('download') {
           steps {
                sh "ls"
            }
        }
  stages {
       stage('download') {
             steps {
                  sh 'wget -O /tmp/app.zip https://github.com/roboshop-devops-project/frontend/archive/main.zip'
              }
          }
  stages {
       stage('download') {
             steps {
                  withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
                   sh "aws s3 cp /tmp/app.zip s3://chanti.ch"
                  }
              }
          }


  }
}

