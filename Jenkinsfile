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
			
			library 'my-shared-library@main'
			env.CDD_SERVER_URl= 'http://lvntest002908.bpc.broadcom.net'
         	        sendNotificationToCDDCall projectName: 'MobileBaanking'
			}		
		}
}
