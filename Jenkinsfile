node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/Mav'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean install"
  }
  stage("publish to s3") {
    s3CopyArtifact buildSelector: lastSuccessful(), excludeFilter: '/target', filter: '/var/lib/jenkins/workspace/CiPipelineJob/target/*.jar', flatten: true, optional: true, projectName: 'CiPipelineJob', target: ''
  }
        
}
