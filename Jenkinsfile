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
            mattermostSend(message: 'Nov. 20, Friday \'20', text: 'This is a git merge test message', icon: 'https://www.jenkins.io/images/logos/santa-claus/256.png')
          }
        }

        stage('Comment on an issue') {
          steps {
            jiraComment(issueKey: 'EMMA-15', body: 'Nov. 20, Friday : This is a git merge test comment')
          }
        }

      }
    }

    stage('Request an approval for Git merge') {
      steps {
        input 'Request an approval for git merge test'
      }
    }

    stage('Check Vault Crednetial & Git Merge') {
      steps {
        git(url: 'https://github.com/eunzoo/algostudy/', branch: 'add-test-file')
        withVault(configuration: [vaultUrl: 'https://dodt-vault.acldevsre.de',  vaultCredentialId: 'approle-for-vault', engineVersion: 2], vaultSecrets: [[path: 'jenkins/eunzoo-public-github', secretValues: [[envVar: 'GITHUB_TOKEN', vaultKey: 'token']]]]) {
          sh "echo ${env.GITHUB_TOKEN}"
          sh '''git clone https://${env.GITHUB_TOKEN}@github.com/eunzoo/algostudy.git

git fetch origin
git checkout origin/add-test-file
git merge master

git checkout master
git merge --no-ff add-test-file
git push origin master'''
        }

      }
    }

  }
}