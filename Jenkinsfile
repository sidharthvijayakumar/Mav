node{
  stage('SCM Checout'){
   
  git 'https://github.com/sidharthvijayakumar/Mav'
  }
  stage('Build'){
     def mvnHome = tool name: 'Maven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean install"
  }
   stages {
        stage('Download') {
            steps {
                sh 'echo "artifact file" > generatedFile.txt'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'generatedFile.txt', onlyIfSuccessful: true
        }
}
