
Skip to content

    Pull requests
    Issues
    Marketplace
    Explore

    @arzvi

1
0

    0

arzvi/jenkinstest
Code
Issues 0
Pull requests 0
Projects 0
Wiki
Insights
Settings
jenkinstest/Jenkinsfile
5f24479 a minute ago
@arzvi arzvi Update Jenkinsfile
39 lines (38 sloc) 817 Bytes
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
    stage('Deploy') {
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message "Which version?"
        ok "Deploy"
        parameters{
          choice(name: 'APP_VERSION', choices:"v1\nv2\nv3", description: 'What to deploy?')
        }
      }
      steps {
        echo 'Deploying ${APP_VERSION}'
      }
    }
  }
  environment {
    nameID = 'Arun'
    todayNum = '20181030'
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
