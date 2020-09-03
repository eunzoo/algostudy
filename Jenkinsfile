pipeline {
  agent any
  stages {
    stage('Get Issue') {
      steps {
        jiraGetProject 'EMMA-12'
        jiraAddComment(idOrKey: 'EMMA-12', comment: 'jenkins pipeline test')
      }
    }

  }
}