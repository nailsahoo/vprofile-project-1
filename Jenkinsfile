pipeline {
    
	agent any
	
	tools {
	jdk "jdk17"

        maven "maven3.9"

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
                sh 'mvn -s setting.xml -DskipTests install'
            }
            
	    }
	   }
	  }
