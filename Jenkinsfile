pipeline {
  agent {
    label 'jdk10'
  }
  stages {
    stage('Say Hello') {
      steps {
        sh 'echo "$nameID is my name. $todayNum is the date"'
        sh 'java -version'
      }
    }
  }
  environment {
    nameID = 'Arun'
    todayNum = '20181030'
  }
}