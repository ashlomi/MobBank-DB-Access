library 'JenkinsFiles'
properties([
 pipelineTriggers([githubPush()]),
 parameters([
   string(defaultValue: 'http://lvntest002908.bpc.broadcom.net:8080', description: '', name: 'CDD_SERVER_URL', trim: true),
   string(defaultValue: '00000000-0000-0000-0000-000000000000', description: '', name: 'CDD_TENANT_ID', trim: true)])
 ])
params.each { k, v -> env[k] = v }
pipeline {
 agent {
  label 'master'
 }
 stages {
  stage('Checkout') {
   steps {
    echo "***Build***"
    sh "./gradlew clean build"
   }
  }
   
stage('NexusArtifactUploaderJob') {
    steps {
      script {
//nexusArtifactUploader artifacts: [[artifactId: 'dummy', classifier: '', file: 'build/libs/dummy.war', type: 'war']], credentialsId: 'Nexus_admin', groupId: 'dummy', nexusUrl: 'ibndev003773.bpc.broadcom.net:8080/nexus', nexusVersion: 'nexus2', protocol: 'http', repository: 'Online-Payments', version: '1.0'
      }
    }
  }
 
 }
 post {
  success {
    sendNotificationToCDDCall projectName: 'MobileBanking', scope: 'BUSINESS_APPLICATION', businessApplicationName: 'Biometric Payment', fileSourceBranchName: 'master'
  }
 }
}
