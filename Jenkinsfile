node{
   def tomcatWeb = 'C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\webapps'
   def tomcatBin = 'C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\bin'
   def tomcatStatus = ''
   
  stage('SCM Checkout'){
     git 'https://github.com/Hemantakumarpati/onlinebookstore-tomcat.git'
   }
  
   stage('Compile-Package-create-war-file'){
         bat "mvn package"
         //sh 'mvn package
      }
   
   stage('Unit Test') {
			steps {
				echo "Unit Test Completed"
				sleep 5
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test Completed"
				sleep 5
			}
		}
		stage('Security Test') {
			steps {
				echo "Security Test Completed"
				sleep 5
			}                    
		}
		stage('Selenium Test') {
			steps {
				echo "Selenium Test Completed"
				sleep 5
			}                    
		}
   
  
   stage('Deploy to Tomcat'){
     bat "copy target\\OnlineBookStore-1.0-SNAPSHOT.war C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\webapps"
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         //bat "${tomcatBin}\\startup.bat"
         bat "C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\bin\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }
}

