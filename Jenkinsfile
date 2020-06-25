

stage('Build') {
   steps {
       echo 'Building...'
   }
   post {
       always {
           jiraSendBuildInfo site: 'amanhie.atlassian.net'
       }
   }
}
stage('Deploy - Production') {
   when {
       branch 'master'
   }
   steps {
       echo 'Deploying to Production from master...'
   }
   post {
       always {
           jiraSendDeploymentInfo site: 'amanhie.atlassian.net', environmentId: 'us-prod-1', environmentName: 'us-prod-1', environmentType: 'production'
       }
   }
}

