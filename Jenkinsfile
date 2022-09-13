node {

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("e-learning-by-SSE/infrastructure-auth-keycloak")
    }
	
    stage('Push image') {
        docker.withRegistry('https://ghcr.io', 'github-ssejenkins') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
