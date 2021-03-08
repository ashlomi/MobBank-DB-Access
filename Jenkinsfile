pipeline {

    environment {
	    CDD_SERVER_PORT = '8080'
	    CDD_SERVER_URl= 'lvntest002908.bpc.broadcom.net'
    }
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
			
			library 'my-shared-library@main'
         	        sendNotificationToCDDCall projectName: 'MobileBaanking', scope: 'BUSINESS_APPLICATION',businessApplicationName: ''
			}		
		}
}
