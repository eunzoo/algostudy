pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('Send a message') {
      steps {
        mattermostSend(message: '2020.11.19 Message', text: 'This is a test alarm.')
      }
    }

  }
}