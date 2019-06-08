pipeline { 
    checkout scm
    env.WORKSPACE = pwd()
    stages {
            stage('build rabbitmq image') {
            def build_image = docker.build("rmq:3.0", "-f Dockerfile .")
    
            build_image.inside {
            
                stage('Test output') {
                    sh "ps -ef"
                }
            }
            }
            
    }                
}
