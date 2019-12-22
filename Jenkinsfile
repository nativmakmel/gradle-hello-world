#!groovy
node('slave1') {
   // Mark the code checkout 'stage'....
   stage ('Checkout'){

      // Get some code from a GitHub repository
      checkout scm
      
   }

   // Mark the code build 'stage'....
   stage ('Build Gradle'){
      // Get the maven tool.
      // ** NOTE: This 'maven3' maven tool must be configured
      // **       in the global configuration.
      def mvnHome = tool 'Gradle 4.10.3'
      // Run the maven build
      sh "${mvnHome}/bin/mvn clean install"
   }
   
    post {
     always {
         // archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true, allowEmptyArchive: true
     }
}
}
