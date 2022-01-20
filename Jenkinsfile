node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/sandeep22y/Snykscriptbasedintegration.git'
      mvnHome = tool 'MVN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            sh(/"%MVN_HOME%/usr/share/maven" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '2369d940-258f-435d-aacd-672d45619d61', snykInstallation: 'Snyk', snykTokenId: 'Snyk'
       
   }

}
