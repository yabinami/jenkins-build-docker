node{
  def app

    stage('clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        docker.image('xavki/nginx').withRun('-p 8080:8080') { c ->
        sh 'docker ps'
	sh ' curl localhost'
    }
    }
}
