pipeline {
  agent any
    environment {
      AWS_DEFAULT_REGION='us-west-1'
      CREDS=credentials('AWS')
  }

  tools {nodejs "NodeJS"}

  
  stages {
    stage("build") {
      steps {
        //git credentialsId: 'GitHub', url: 'https://github.com/Yasaswini720/React_Tutorial_Contact_Manager_App.git'
        bat 'npm install'
        bat 'npm run build'
      }}
      
    stage("test") {
      steps {
      echo '************This is test script***********'
      }}

    stage("deploy") {
      steps {
        bat 'aws s3 sync ./build s3://demoooooo'
          
      }}
}
  
  post {

  always {echo 'Post stage'}
  success {
    mail bcc: '', body: "<b>Project Status - Your project pipeline ran successfully.</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: 'yasaswini720@gmail.com', mimeType: 'text/html', replyTo: '', subject: "Success: Project Successfully builded", to: "yasaswini720@gmail.com";
  }
  failure {
    mail bcc: '', body: "<b>Project Status - Your project pipeline has failed.</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: 'yasaswini720@gmail.com', mimeType: 'text/html', replyTo: '', subject: "ERROR: Project pipeline failed", to: "yasaswini720@gmail.com";
  }}
}
