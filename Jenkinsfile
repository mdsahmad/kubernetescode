node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("shahidahmad/pythontestapp")
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'shahidahmad') {
            app.push("${env.BUILD_NUMBER}")
        }
    }

}
