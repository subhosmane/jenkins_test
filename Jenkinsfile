node('docker') {
    checkout scm
    env.WORKSPACE = pwd()
    sh "mkdir -p ${env.WORKSPACE}/_artifacts"
    stage('build docker image') {
        def build_image = docker.build("nginx.8.0", "-f Dockerfile .")


    // Run a Test
    
        build_image.inside {
            
            stage('test') {
                sh "nginx version"
            }
        }
      }
    }
