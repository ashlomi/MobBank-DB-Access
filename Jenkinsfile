library 'JenkinsFiles'
properties([
 pipelineTriggers([githubPush()]),
// parameters([
 //string(defaultValue: 'http://lvntest002908.bpc.broadcom.net:8080', description: '', name: 'CDD_SERVER_URL', trim: true),
 //string(defaultValue: '00000000-0000-0000-0000-000000000000', description: '', name: 'CDD_TENANT_ID', trim: true)])
 string(defaultValue: 'https://cddirector.io:443', description: '', name: 'CDD_SERVER_URL', trim: true),
string(defaultValue: 'dd956bb5-1be0-4855-8606-c515c7926e0c', description: '', name: 'CDD_TENANT_ID', trim: true)])
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
   }
  }
   

 
 }
 post {
  success {
    sendNotificationToCDDCall projectName: 'MobileBanking'
  }
 }
}
