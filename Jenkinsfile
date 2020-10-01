node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/Mav'
  }
  stage('Comiple-Package'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean package"
  }
}
