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
    docker.withRegistry(\'https://10.1.53.4/\',\'dtr-login\'){
       // dtr-login is a login ID in credentials 
        stage "syncing files"
        git \'https://github.com/reshma-k/example-voting-app.git/\'
        stage "Building and pushing Vote Image"
        def vote_img = docker.build(\'dockeradmin/voting-app-vote\',\'./vote\').push(\'latest\')
        }
}'''
        }
      }
    }
  }