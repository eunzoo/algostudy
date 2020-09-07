pipeline {
  agent any
  stages {
    stage('Send Message') {
      steps {
        mattermostSend(message: 'what time is it now?', icon: 'http://www.mattermost.org/wp-content/uploads/2016/04/icon.png')
      }
    }

  }
}