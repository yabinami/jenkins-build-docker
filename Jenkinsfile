node{
  def app
    stage('clone') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build("nginx:latest")
    }
    stage('Run image') {
        docker.image('nginx:latest').withRun('-p 80:80') { c ->
        sh 'docker ps'
	sh ' docker exec -ti youthful_chatterjee bash && cat /etc/nginx/conf.d/default.conf '
    }
    }
}
