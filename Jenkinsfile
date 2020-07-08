node{
    def app
    
    stage('Clone repository"){
        
        checkout scm
    }
    
    stage('Build image') {
        
        app = docker.build("AMw007/DevOps_tu")
    }
    
    stage('Test image') {
        
        app.inside {
            sh 'echo "Tests passed"'
        }
    }
    
    stage('Push image) {
    
        docker.withRegistry('https://registry.huv.docker.com','Dockerhub') {
            add.push("$env.BUILD_NUMBER)")
            add.push("latest")
        }
   }
}
