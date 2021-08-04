node{
  def app
    stage('clone') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build("nginx:latest")
    }
    stage('Run image') {
        docker.image('nginx:latest').withRun('-p 8081:8081') { c ->
        sh 'docker ps'
	sh 'curl localhost'
    }
    }
}
