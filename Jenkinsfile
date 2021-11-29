pipeline {
  agent any
  stages {
    stage('Prep') {
      steps {
        echo "Hello"
      }
    }
  }
  post {
    success {
      script {
        if (env.CHANGE_ID) {
          githubNotify status: 'SUCCESS'
        }
      }
    }
    failure {
      script {
        if (env.CHANGE_ID) {
          githubNotify status: 'FAILURE'
        }
      }
    }
  }
}
