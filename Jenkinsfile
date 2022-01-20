node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/sandeep22y/Snykscriptbasedintegration.git'
      mvnHome = tool 'Maven home'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["Maven home=$mvnHome"]) {
            sh(/"%Maven home%\usr\share\maven" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '2369d940-258f-435d-aacd-672d45619d61', snykInstallation: 'Snyk', snykTokenId: 'Snyk'
       
   }

}
