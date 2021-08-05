node{
  def app

    stage('clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        docker.image('xavki/nginx').withRun('-p 80:80') { c ->
        sh ' curl localhost'
        sh 'docker ps'

    }
    }
}
