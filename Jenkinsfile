node {
	def app

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build(hubbaduck/dkr-jnks-course)
	}

	stage('Push image') {
		docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
			app.push(2.0.0)
		}
	}
}