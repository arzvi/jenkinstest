pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        sh 'echo "$nameID is my name"'
        sh 'java -version'
      }
    }
  }
  environment {
    nameID = 'Arun'
  }
}