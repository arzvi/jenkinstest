pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        sh 'echo "$nameID is my name. $todayNum is the date"'
        sh 'java -version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
  }
  environment {
    nameID = 'Arun'
    todayNum = '20181030'
    TEST_USER = credentials('test-user')
  }
}