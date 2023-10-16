pipeline {
  agent any
  tools { 
       	maven 'mvn-3.9.5' 
       	jdk 'jdk17'
    	}
  stages {
    
 
   
    stage('Deploy CloudHub') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        sh 'mvn clean deploy -DskipTests -DmuleDeploy  -Dmule.version=4.4.0 -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}' 
      }
    }
  }
}