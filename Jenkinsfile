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
			env.CDD_SERVER_PORT = '443'
			env.CDD_SERVER_URl= 'lvntest002908.bpc.broadcom.net'
			library 'my-shared-library@main'
         	        sendNotificationToCDDCall projectName: 'MobileBaanking', scope: 'APPLICATION', businessApplicationName: 'Mobile Banking'
			}		
		}
}
