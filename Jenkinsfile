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

    stage('build') {
      steps {
        bat 'nuget restore .\\src\\MyWindowsService\\ -source "https://api.nuget.org/v3/index.json"'
      }
    }

    stage('deploy') {
      steps {
        bat 'msbuild .\\src\\MyWindowsService\\MyWIndowsService\\Deploy-Windows-Service-Via-MSBuild.proj'
      }
    }

  }
}