pipeline {
  agent any
  stages {
    stage('CHeckout Code') {
      steps {
        git(url: 'https://github.com/khanh291999/curriculum-app', branch: 'dev')
      }
    }

    stage('Log the directory') {
      steps {
        sh 'ls -la'
      }
    }

  }
}