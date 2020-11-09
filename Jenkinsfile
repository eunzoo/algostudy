pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('error') {
      steps {
        mattermostSend(message: '2020.11.09 Message', text: 'This is a test alarm.')
      }
    }

  }
}