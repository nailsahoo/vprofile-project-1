pipeline {
    
	agent any
	
	tools {
	jdk "JDK17"

        maven "MAVEN"

    }
	
    environment {
    SNAP_REPO      = 'my-project-repo'
    RELEASE_REPO   = 'my-project-repo'
    CENTRAL_REPO   = 'maven-central'
    NEXUS_GRP_REPO = 'maven-public'
    NEXUSIP        = '172.31.31.195'
    NEXUSPORT      = '8081'
    NEXUS_LOGIN    = 'nexuslogin'
}

	
    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            
	    }
	   }
	  }
