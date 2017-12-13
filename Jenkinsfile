pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh '''pwd
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
        sh '''ant -Ddst=/var/www/html/dl.gawati.org/jenkins provide
'''
      }
    }
    stage('Clean') {
      steps {
        cleanWs(cleanWhenAborted: true, cleanWhenNotBuilt: true, cleanWhenSuccess: true, cleanWhenUnstable: true, cleanupMatrixParent: true, deleteDirs: true)
      }
    }
  }
}