pipeline {
  agent {
    node {
      label 'slave'
    }

  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    stage('test1') {
      parallel {
        stage('test1') {
          steps {
            sh 'npm run test1'
          }
        }
        stage('test2') {
          steps {
            sh 'npm run test2'
          }
        }
        stage('test3') {
          steps {
            sh 'npm run test3'
          }
        }
      }
    }
    stage('build docker') {
      steps {
        sh 'docker build -t lifnadia/multiplication-service:latest .'
      }
    }
    stage('push') {
      steps {
        sh '''docker login -u lifnadia -p lifnadia29
docker push lifnadia/multiplication-service:latest

'''
      }
    }
  }
}