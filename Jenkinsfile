node{
   def tomcatWeb = 'C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\webapps'
   def tomcatBin = 'C:\\apache-tomcat-10.0.0-M5-windows-x64\\apache-tomcat-10.0.0-M5\\bin'
   def tomcatStatus = ''
   
  stage('SCM Checkout'){
     git 'https://github.com/Hemantakumarpati/onlinebookstore-tomcat.git'
   }
  
   stage('Compile-Package-create-war-file'){
         bat "mvn package"
      }
   
   //push war file to artifactory
   //Code checking with sonarqube
   //veracode security
   //Docker build
   //Docker push
   //Kubernetes deployment
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

