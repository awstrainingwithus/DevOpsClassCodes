pipeline{
   agent any
   tools {
        maven "maven3.8" // You need to add a maven with name "3.6.0" in the Global Tools Configuration page
    }
   stages{
   stage('Checkout Stage'){
      
      steps{
            echo "SCM Checkout Started"
	        script{
		            git 'https://github.com/awstrainingwithus/DevOpsClassCodes.git'
	            }
            echo "SCM Checkout Completed"
      }
   }
   
    stage('Build Stage'){
      steps{
     script{
	 sh "mvn -version"
	 sh "mvn package"
	 echo"Build Stage is Completed"
	 }
   }
   }
   

   
}
}
