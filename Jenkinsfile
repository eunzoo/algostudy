pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        mattermostSend(message: '2020.10.14 Message', text: 'This is a test alarm.')
      }
    }

  }
}