pipeline {
   agent {
     label 'server1'
   }
  stages {
     stage('download') {
           steps {
                sh 'wget https://github.com/roboshop-devops-project/frontend/archive/main.zip'
            }
        }

  }
}

