node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'mymavan', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Abhijeet''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'traningsanyal06@gmail.com'
   }
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/',
       channel: '#jenkins-pipeline-demo',
       color: 'good',
       message: 'Welcome to Jenkins, Slack!',
       teamDomain: 'javahomecloud',
       tokenCredentialId: 'slack-demo'
   }
}
