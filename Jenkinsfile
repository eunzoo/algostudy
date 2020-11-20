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

    stage('git checkout add-test-file') {
      steps {
        git(url: 'https://github.com/eunzoo/algostudy', branch: 'tree/add-test-file')
      }
    }

    stage('Request an approval for Git merge') {
      steps {
        input 'Request an approval for git merge test'
      }
    }

    stage('Check Vault Crednetial') {
      steps {
        withVault(configuration: [vaultUrl: 'https://dodt-vault.acldevsre.de',  vaultCredentialId: 'approle-for-vault', engineVersion: 2], vaultSecrets: [[path: 'jenkins/eunzoo-public-github', secretValues: [[envVar: 'GITHUB_TOKEN', vaultKey: 'token']]]]) {
          sh "echo ${env.GITHUB_TOKEN}"
        }

      }
    }

    stage('Git merge') {
      steps {
        gitAutomerger(checkoutFromRemote: true, detailConflictReport: true, logLevel: 'INFO', remoteName: 'add-test-file')
      }
    }

  }
}