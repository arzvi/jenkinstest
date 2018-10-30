pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${params.Name}!"
        sh 'java -version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
    stage('Get Kernel'){
      steps{
        script{
          try{
            USER_NAME= sh(script: 'whoami', returnStdout: true)
          }
          catch(err){
            echo "Caught error: ${err}"
            throw err
          }
        }
      }
    }
    stage('Say Kernel'){
      steps{
        echo "${USER_NAME}"
      }
    }
  }
  environment {
    nameID = 'Arun'
    todayNum = '20181030'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push the button?'

    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
