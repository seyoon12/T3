
node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("535597585675.dkr.ecr.ap-northeast-2.amazonaws.com/wntpqhd")
     }
     stage('Push image') {
         docker.withRegistry('https://535597585675.dkr.ecr.ap-northeast-2.amazonaws.com/wntpqhd', 'ecr:ap-northeast-2:aws-credentials') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("535597585675.dkr.ecr.ap-northeast-2.amazonaws.com/wntpqhd")
}

stage('Push image') {
  docker.withRegistry('https://535597585675.dkr.ecr.ap-northeast-2.amazonaws.com/wntpqhd', 'ecr:ap-northeast-2:aws-credentials') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}
