pipeline {
  agent any
  stages {
    stage('synching files') {
      steps {
        echo 'synching files'
      }
    }
    stage('Building and pushing vote image') {
      steps {
        sh '''{
        stage "Building and pushing Vote Image"
        def vote_img = docker.build(\'dockeradmin/voting-app-vote\',\'./vote\').push(\'latest\')
    }
}'''
        }
      }
    }
  }