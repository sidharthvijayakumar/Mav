node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/Mav'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean install"
  }
  stage("publish to s3") {
    s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 's3-artifactsforjenkins', excludedFile: '/target', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'ap-southeast-1', showDirectlyInBrowser: false, sourceFile: '**/target/*.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'S3-Artifact', userMetadata: []  
  }
  stage("Email"){
   mail bcc: '', body: 'Build results', cc: '', from: '', replyTo: '', subject: 'Jenkins-CiPipelineJob', to: 'sidharthvijayakumar7@gmail.com' 
  }
  
  
}
