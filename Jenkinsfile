node {
    def sparky-keycloak-auth

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("ssedevelopment/sparky-keycloak-auth")
    }
	
    stage('Push image') {
        docker.withRegistry('https://ghcr.io', '2ad31065-44e1-4850-a3b1-548e17aa6757') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}