node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      //mvnHome = tool 'M3'
   }
   stage('Build Zip package'){
       dir("${JENKINS_HOME}/appian/appian-adm-versioning-client"){
           sh "rm -rf ${JENKINS_HOME}/appian/packages/*"
           sh "sh ./version-application.sh"
           
       }
   }
   stage('Deploy') {
         dir("${JENKINS_HOME}/appian/appian-adm-import-client-2.5.3") {
            sh "sh ./deploy-application.sh"
         }
   }
  
}
