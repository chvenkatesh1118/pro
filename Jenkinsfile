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

       stage('download') {
             steps {
                  sh 'wget -O /tmp/app/app.zip https://github.com/roboshop-devops-project/frontend/archive/main.zip'
              }
          }
  stages {
       stage('download') {
             steps {
                  s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'chanti.ch', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-iso-east-1', showDirectlyInBrowser: false, sourceFile: '/tmp/app', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'chantiartifact', userMetadata: []
                  }
              }
          }


  }
}

}