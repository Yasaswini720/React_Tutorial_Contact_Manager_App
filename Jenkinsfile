// pipeline {
//   agent any
  
//   stages {
//     stage("build") {
//       steps {
//       echo 'building'
//       }
//     }
//   }
// }
  
pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
    }
}
