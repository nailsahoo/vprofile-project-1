pipeline {
    
	agent any
	
	tools {
	jdk "JDK17"

        maven "MAVEN"

    }
	
    environment {
    SNAP_REPO      = 'my-project-repo'
    RELEASE-REPO   = 'my-project-repo'
    CENTRAL-REPO   = 'maven-central'
    NEXUS-GRP-REPO = 'maven-public'
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
