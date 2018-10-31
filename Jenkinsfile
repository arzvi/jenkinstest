pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('outer') {
      steps {
        echo 'outside'
        sh 'printenv'
      }
    }
    stage('Mine') {
      environment {
        AN_ACCESS_KEY = credentials('an_access_key')
      }
      steps {
        echo 'Inside'
        sh 'printenv'
      }
    }
  }
  environment {
    CC = 'cland1'
  }
}