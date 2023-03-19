pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/soms8020 will replace by sed command before RUN
        git url: 'https://github.com/soms8020', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}