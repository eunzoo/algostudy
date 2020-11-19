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
      parallel {
        stage('Send a message') {
          steps {
            mattermostSend(message: 'Nov. 19, Thursday \'20', text: 'This is a git merge test message')
          }
        }

        stage('Comment on an issue') {
          steps {
            jiraComment(issueKey: 'EMMA-14', body: 'Nov. 19, Thursday : This is a git merge test comment')
          }
        }

      }
    }

    stage('Request an approval for Git merge') {
      steps {
        input(message: 'Request an approval for Git merge', submitter: 'jmungmoong.roh')
      }
    }

    stage('Git merge') {
      steps {
        gitAutomerger(logLevel: 'INFO', detailConflictReport: true, checkoutFromRemote: true, remoteName: 'origin/add-test-file')
      }
    }

  }
}