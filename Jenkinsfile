pipeline {
  agent {
    node {
      label 'jenkins-jenkins-slave'
    }

  }
  stages {
    stage('Send a message') {
      parallel {
        stage('Send a message') {
          steps {
            mattermostSend(message: '2020.11.19 Message', text: 'This is a test alarm.')
          }
        }

        stage('Request an approval') {
          steps {
            input(message: 'Approval Test', submitter: '58250262+mungmoong3')
          }
        }

      }
    }

  }
}