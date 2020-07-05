pipeline{
   agent any
   tools {
        maven "maven363" // You need to add a maven with name "maven363" in the Global Tools Configuration page
    }
   stages{
   stage('Checkout Stage'){
      
      steps{
            echo "SCM Checkout Started"
	        script{
		            git 'https://github.com/awstrainingwithus/DevOpsClassCodes.git'
		            slackSend channel: '#testproject', message: "SCM Checkout Completed for build # ${BUILD_NUMBER}"

	            }
            echo "SCM Checkout Completed"
      }
   }
   stage('Build Stage'){
      steps{
         script{
	 sh "mvn -version"
     sh "mvn package"
	 slackSend channel: '#testproject', message: 'Build Completed $BUILD_NUMBER'
	 }
   }
   }
   
   stage('Slack Notification'){
	   steps{
	   script{
	
       slackSend channel: '#testproject', 
       message: "Package creation is successful for ${JOB_NAME}. Click on the URL to view more details ${JOB_URL}"
	   }
	   }
   }
   
}
}
