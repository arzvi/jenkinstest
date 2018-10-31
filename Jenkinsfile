pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('outer') {
      steps {
        echo 'outside'
        sh '''echo "AN_ACCESS_KEY_USR" > /tmp/mine


'''
        sh 'cat /tmp/mine'
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