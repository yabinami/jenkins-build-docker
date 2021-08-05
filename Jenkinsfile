node{
  def app

    stage('clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("xavki/nginx")
    }

    stage('Run image') {
        sh '''
	          docker run -d -p 80:80 xavki/nginx
            docker ps
	          curl localhost
	         '''
    }
}
