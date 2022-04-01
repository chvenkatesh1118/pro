pipeline {
   agent {
     label 'server1'
   }
  stages {
     stage('clean') {
           steps {
                sh "ls"
            }
        }

       stage('download') {
             steps {
                  sh 'wget -O /tmp/app.1.zip https://github.com/roboshop-devops-project/frontend/archive/main.zip'
              }
          }

       stage('upload') {
             steps {
                  s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'chanti.ch', excludedFile: '/tmp', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-iso-east-1', showDirectlyInBrowser: false, sourceFile: '**/tmp/*.zip', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'chantiartifact', userMetadata: []
              }
          }


  }


