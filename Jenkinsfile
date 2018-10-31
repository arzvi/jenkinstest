pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('outer') {
      steps {
        echo 'outside'
        tee(file: '/tmp/mine') {
          sh 'echo "${AN_ACCESS_KEY_USR}"'
          echo 'This is the day'
        }

      }
    }
    stage('Mine') {
      environment {
        AN_ACCESS_KEY = credentials('an_access_key')
      }
      steps {
        echo 'Inside'
        sh 'cat /tmp/mine'
      }
    }
  }
  environment {
    CC = 'cland1'
  }
}