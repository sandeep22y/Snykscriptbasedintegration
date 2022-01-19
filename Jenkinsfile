node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/cltalam/Snykscriptbasedintegration.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '2369d940-258f-435d-aacd-672d45619d61', snykInstallation: 'Snyk', snykTokenId: 'Snyk'
       
   }

}
