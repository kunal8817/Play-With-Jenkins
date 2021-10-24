pipeline {
  agent { label 'kubepod' }

  stages {
    stage('Checkout Source') {
      steps {
        git branch: 'main', changelog: false, poll: false, url: 'https://github.com/kunal8817/Play-With-Jenkins'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }
    
  }
}
