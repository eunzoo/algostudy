pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'This is a message.', text: 'Text comes from a bot named Workflowbot.')
      }
    }

    stage('Jira Add Comment') {
      steps {
        jiraAddComment(idOrKey: 'EMMA-14', comment: 'Send webhook message', input: 'Send webhook message')
        jiraComment(issueKey: 'EMMA-14', body: 'Send webhook message')
      }
    }

  }
}