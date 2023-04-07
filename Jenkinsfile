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
        git credentialsId: 'GitHub', url: 'https://github.com/Yasaswini720/React_Tutorial_Contact_Manager_App.git'
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
}
