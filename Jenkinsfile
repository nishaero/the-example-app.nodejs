pipeline {
    agent any
    tools {
        nodejs 'nodejs3'
    }
    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '15', 
                    numToKeepStr: '10'
            )
    }

    environment {
        APP_NAME = "SAMPLE_NODEJS_APP"
        APP_ENV  = "DEV"
    }
    stages {
         stage('Cleanup Workspace') {
            steps {
                cleanWs()
                sh """
                echo "Cleaned Up Workspace for ${APP_NAME}"
                """
            }
        }
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
