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
          pullRequest.removeLabel('Fail')
          pullRequest.addLabel('Pass')
        }
      }
    }
    failure {
      script {
        if (env.CHANGE_ID) {
          pullRequest.removeLabel('Pass')
          pullRequest.addLabel('Fail')
        }
      }
    }
  }
}
