pipeline {
  agent any
  stages {
    stage('Prep') {
      steps {
        echo "Hello"
        sh "/opt/apache-maven-3.6.3/bin/mvn clean install"
      }
    }
  }
}
