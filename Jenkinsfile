pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  options {
    timeout(time: 100, unit: 'SECONDS')
  }
  stages{
    stage("Cleanup Workspace"){
            steps {
            cleanWs()
            }
    }
  
   stage("Checkout from SCM"){
           steps {
           git branch: 'main', credentialsId: 'github' , url: 'https://github.com/VikneshVickiizz/VikneshVickiizz'
           }
   }  
   stage("Build Application"){
           steps {
           sh "mvn clean package"
           }
   }
  stage("Test Application"){
           steps {
           sh "mvn test"
           }
   }
}
}
