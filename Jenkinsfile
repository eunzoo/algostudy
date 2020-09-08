pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'what time is it now?', icon: 'ghost', text: 'comes from a bot named Workflowbot.')
      }
    }

  }
}