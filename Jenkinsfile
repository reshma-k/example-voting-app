pipeline {
  agent any
  stages {
    stage('Synching files') {
      steps {
        load 'node {     docker.withRegistry(\'https://10.1.53.4/\',\'dtr-login\'){        // dtr-login is a login ID in credentials          stage "syncing files"         git \'https://github.com/reshma-k/example-voting-app.git/\'          stage "Building and pushing Vote Image"         def vote_img = docker.build(\'dockeradmin/voting-app-vote\',\'./vote\').push(\'latest\')          stage "Building and pushing Worker Image"         def worker_img = docker.build(\'dockeradmin/voting-app-worker\',\'./worker\').push(\'latest\')          stage "Building and pushing Result Image"         def result_img = docker.build(\'dockeradmin/voting-app-result\',\'./result\').push(\'latest\')     } }'
      }
    }
    stage('Building and vote app') {
      steps {
        sh '''node
{
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