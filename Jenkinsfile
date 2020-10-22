pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('error') {
      steps {
        mattermostSend(message: '2020.10.14 Message', text: 'This is a test alarm.')
      }
    }

  }
  environment {
    EUNZOO_KEY = 'EMMA'
  }
}