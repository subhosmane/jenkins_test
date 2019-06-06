node('master') { 
    checkout scm
    env.WORKSPACE = pwd()
    sh "mkdir -p ${env.WORKSPACE}/_artifacts"
    stage('build rabbitmq image') {
        def build_image = docker.build("rmq:3.0", "-f Dockerfile .")


    // Run a Test
    
        build_image.inside {
            
            stage('Test output') {
                sh "rabbitmqctl list_users"
            }
        }
      }
    }
