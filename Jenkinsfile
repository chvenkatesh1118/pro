pipeline {
   agent {
     label 'server1'
   }
  stages {
        stage('clean') {
             steps {
                sh "rm -rf /tmp/app"
                sh "mkdir /tmp/app"
              }
           }


       stage('download') {
             steps {
                  sh 'wget -O /tmp/app/app.1.zip https://github.com/roboshop-devops-project/frontend/archive/main.zip'
              }
          }
       stage('change') {
                  steps {
                       sh "cd /tmp/app"
                   }
               }

//        stage('upload') {
//              steps {
//                  s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'chanti.ch', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '**/*.zip', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'chantiartifact', userMetadata: []
//               }
//           }
            stage('upload to nexus') {
                 steps {
                 nexusArtifactUploader artifacts: [[artifactId: 'nexusartifact', classifier: '', file: '/tmp/app/app.1.zip', type: 'zip']], credentialsId: 'admin', groupId: 'groupid', nexusUrl: '172.31.2.200', nexusVersion: 'nexus3', protocol: 'http', repository: 'http://18.212.193.226:8081/repository/chanti.ch/', version: '1
                 }
              }



  }
}
