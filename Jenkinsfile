node{
  stage('SCM Checkout'){  
  git 'https://github.com/abishek9114/my-app.git'
  }
  
  stage('Compile-Package'){
    def mvnHome = tool name: 'maven-plugin', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  stage('Email-Notification'){
  mail bcc: '', body: '''Hi, 
  This is to inform you that a jenkins job has been completed. Please check the status in the console.
  Regards
  Abhishek
  ''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job Status', to: 'aws2020.study@gmail.com'
  }
  stage('Slack-Notification){
        slackSend baseUrl: 'https://hooks.slack.com/services/', 
        channel: '#jenkins-pipeline-practice', 
        color: 'good', 
        message: 'Job Creation Status', 
        tokenCredentialId: 'slack-demo'
        
        }


}
