pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'This is the town message.', text: 'text', channel: 'Town-Square')
      }
    }

    stage('Jira Add Comment') {
      steps {
        jiraComment(issueKey: 'EMMA-14', body: 'Send webhook message')
      }
    }

  }
}