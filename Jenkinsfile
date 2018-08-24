pipeline {
  agent any
  stages {
    stage('hello') {
      environment {
        TEST_USER_USR = 'foo'
        TEST_USER_PSW = 'foo_p'
      }
      steps {
        echo "hello ${parameter.name}"
        sh 'java --version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
    stage('Deploy') {
      agent any
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'Should we conntinue?'
      }
      steps {
        echo 'Continuing with deployment'
      }
    }
  }
  environment {
    MY_NAME = 'Brian'
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'who are you', description: 'Who should I greet?')
  }
}