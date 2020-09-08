pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'This is a message.', text: 'Text comes from a bot named Workflowbot.')
      }
    }

  }
}