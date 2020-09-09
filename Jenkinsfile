pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'This is the third message.', text: 'Text comes from a bot named Workflowbot.')
      }
    }

    stage('Jira Add Comment') {
      steps {
        jiraComment(issueKey: 'EMMA-14', body: 'Send webhook message')
      }
    }

    stage('test:comment') {
      steps {
        jiraAddComment(idOrKey: 'emma-14', comment: 'test', input: 'test')
      }
    }

  }
}