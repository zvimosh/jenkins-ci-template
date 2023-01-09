pipeline {
  agent {
    node {
      label 'Windows2022'
    }

  }
  stages {
    stage('checkout-code') {
      agent {
        node {
          label 'Windows2022'
        }

      }
      steps {
        git(url: 'git@github.com:zvimosh/jenkins-ci-template.git', branch: 'master', credentialsId: 'zvi-github')
      }
    }

  }
}