node {
     stage('Clone') {
         checkout scm
     }
     stage('Build') {
         app = docker.build("chaechae0322/hello-jenkins")
	 // app = docker.build("<계정명>/<저장소명>")
     }
     stage('Push') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker_hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
 }
