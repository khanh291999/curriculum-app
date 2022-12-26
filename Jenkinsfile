pipeline {
  agent any
  stages {
    stage('CHeckout Code') {
      steps {
        git(url: 'https://github.com/khanh291999/curriculum-app', branch: 'dev')
      }
    }

    stage('Log the directory') {
      parallel {
        stage('Log the directory') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-end Unit Tests') {
          steps {
            sh 'echo "Unit tests"'
          }
        }

      }
    }

    stage('Build image') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . -t quockhanh0209/curriculum-front'
      }
    }

    stage('Log into Dockerhub') {
      environment {
        DOCKERHUB_USER = ''
        DOCKERHUB_PASSWORD = ''
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

    stage('Push to dockerhub') {
      steps {
        sh 'docker push quockhanh0209/curriculum-front:latest'
      }
    }

  }
  environment {
    DOCKERHUB_USER = 'quockhanh0209'
    DOCKERHUB_PASSWORD = 'Kh@nh02091999'
  }
}