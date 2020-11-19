pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('Request an approval') {
      steps {
        input(message: 'Request an approval for sending a message', submitter: 'jmungmoong.roh')
      }
    }

    stage('Send a message') {
      steps {
        mattermostSend(message: 'Nov. 19, Thursday \'20', text: 'This is a test message')
      }
    }

  }
}