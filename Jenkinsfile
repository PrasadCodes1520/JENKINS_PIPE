pipeline {
         agent any
         tools{
                  maven "maven_home"
         }
         stages {
                 stage('Stage 1 - Checkout Code') {
		        steps {
			        echo 'Hi, this is first pipeline with maven'         
                 }
                 }
                 stage('Stage 2 - Compile Code') {
                 steps {
                    input('Do you want to proceed?')
		        bat "mvn compile"
                 }
                 }
                 stage('Stage 3 - Run Unit Test') {
                 steps {
                       echo "Running Unit Test"
		        bat "mvn test"
	        }
                 }
                 stage('Stage 4 - Create Build') {
                           steps {
                                echo "Creating a build"
				bat "mvn package"
                  }
	        }
		post{
		failure{
			echo "Email has been sent for jenkins build failed"
		}
		}
	}
}
         	
                          
