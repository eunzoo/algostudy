pipeline {
  agent any
  stages {
    stage('Get Issue') {
      steps {
        jiraAddComment(idOrKey: 'EMMA-12', comment: 'jenkins pipeline test', input: 'jenkins pipeline test')
      }
    }

  }
}