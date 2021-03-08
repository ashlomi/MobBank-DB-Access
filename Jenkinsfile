pipeline {
  
    agent {
        label "master"
	}
    stages {
        stage("Export Porject") {
            steps {
             echo '**** mvn Build****'
			}
        }
        stage("Zip Project") {
            steps {
                echo '**** mvn Build****'    
            }
        }
        stage("Publish to Nexus") {
            steps {
			  echo "*** nexusVersion*****"       
			}
		}
	}		
    post { 
		success { 
			@Library('my-shared-library')
         	        sendNotificationToCDDCall projectName: 'MobileBaanking', scope: 'BUSINESS_APPLICATION', businessApplicationName: 'Mobile Banking'
			}		
		}
}
