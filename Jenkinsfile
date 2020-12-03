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
            mattermostSend(message: 'Dec 3, Thursday \'20', text: 'This is a git - algostudy - test message', icon: 'https://www.jenkins.io/images/logos/santa-claus/256.png', endpoint: 'https://mattermost.acldevsre.de/hooks/1oj1jtrkwi81pe1crj3hwbyohe')
          }
        }

        stage('Comment on an issue') {
          steps {
            jiraComment(issueKey: 'EMMA-16', body: 'Dec. 3, Thursday : This is a git merge test comment')
          }
        }

      }
    }

    stage('Check Vault Crednetial & Git Merge') {
      steps {
        withVault(configuration: [vaultUrl: 'https://dodt-vault.acldevsre.de',  vaultCredentialId: 'approle-for-vault', engineVersion: 2], vaultSecrets: [[path: 'jenkins/eunzoo-public-github', secretValues: [[envVar: 'GITHUB_TOKEN', vaultKey: 'token']]]]) {
          sh "echo ${env.GITHUB_TOKEN}"
        }

      }
    }

  }
}