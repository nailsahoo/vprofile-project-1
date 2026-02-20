pipeline {
    
    agent any
    
    tools {
        jdk "JDK17"
        maven "MAVEN"
    }
    
    environment {
        CENTRAL_REPO   = 'maven-central'
        NEXUS_GRP_REPO = 'maven-public'
        NEXUSIP        = '172.31.31.195'
        NEXUSPORT      = '8081'
        NEXUS_LOGIN    = 'nexuslogin'
    }

    stages {

        stage('checkout') {
            steps {
                checkout scm
            }
        }

        stage('BUILD') {
            steps {

                withCredentials([usernamePassword(
                    credentialsId: 'nexuslogin',
                    usernameVariable: 'NEXUS_USER',
                    passwordVariable: 'NEXUS_PASS'
                )]) {

                    sh """
                    mvn -s settings.xml \
                    -DNEXUS_USER=$NEXUS_USER \
                    -DNEXUS_PASS=$NEXUS_PASS \
                    -DNEXUS_IP=$NEXUSIP \
                    -DNEXUS_PORT=$NEXUSPORT \
                    -DNEXUS_GRP_REPO=$NEXUS_GRP_REPO \
                    -DCENTRAL_REPO=$CENTRAL_REPO \
                    -DskipTests install
                    """
                }

            }
        }
    }
}
