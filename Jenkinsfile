pipeline{
  agent{ label:'Jenkins-Agent' }
  tool {
    java: 'Java17',
    maven: 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        cleanWs()
      }
    }
    stage("Checkout from SCM"){
      steps{
        git branch:'main', credentialsId:'github', url:'https://github.com/mitrabhanu-123/basic-webapp'
      }
    }
    stage("Build Application"){
      steps{
        sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps{
        sh "mvn Test"
      }
    }
  }
}
