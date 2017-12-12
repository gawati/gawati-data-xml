pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh '''pwd
ls
ant xar
'''
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
        sh '''ls build
'''
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}