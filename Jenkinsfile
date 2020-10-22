pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('error') {
      steps {
        mattermostSend(message: '2020.10.22 Message', text: 'This is a test alarm.')
      }
    }

  }
}