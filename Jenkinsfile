pipeline {
  agent any
  stages {
    stage('Jira Add Comment') {
      steps {
        jiraComment(issueKey: 'EMMA-14', body: '2020.10.14 another comment')
      }
    }

  }
}