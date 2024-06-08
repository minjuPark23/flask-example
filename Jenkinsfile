node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("minj5541/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker_hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
