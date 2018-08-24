pipeline {
  agent any
  stages {
    stage('hello') {
      steps {
        echo "hello ${parameter.name}"
        sh 'java --version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
  }
  environment {
    MY_NAME = "Brian"
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'who are you',description: 'Who should I greet?' )
  }
}
