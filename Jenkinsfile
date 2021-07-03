node {
	def app
	
	stage('Clone repository') {
		// Cloning the repo to our workspace
	
		checkout scm
	}
	
	stage('Build Image') {
		// This stage would build actual image
	
		app = docker.build("atulp1012/blog_app")
	}

	stage('Push image') {
		// This stage would push the image to docker hub
		
		docker.withRegistry('https://registry.hub.docker.com','e9b07e57-3c23-43f0-bdf5-986d74be47f1') {
		app.push("${env.BUILD_NUMBER}")	
		app.push("latest")
		}
			echo "Trying to push docker image to docker hub"
	}
}
