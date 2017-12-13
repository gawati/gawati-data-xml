pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'pwd'
        sh 'ant xar'
      }
    }
    stage('Test') {
      steps {
        sh 'ls build'
      }
    }
    stage('Deploy') {
      steps {
        sh 'ant -Ddst=/var/www/html/dl.gawati.org/dev provide'
      }
    }
    stage('Clean') {
      steps {
        cleanWs(cleanWhenAborted: true, cleanWhenNotBuilt: true, cleanWhenSuccess: true, cleanWhenUnstable: true, cleanupMatrixParent: true, deleteDirs: true)
      }
    }
  }
}
