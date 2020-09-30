node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/Mav/NewJenkins'
  }
  stage('Comiple-Package'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean"
  }
}
