pipeline {
    agent  {
        label 'agent-1'
    }
    environment { 
        app_version = ''
    }
    options {
        timeout(time: 30, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
    
    // Build
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                        echo "HelloBuild"
                        sleep 10
                        env
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    echo 'Testing..'
                }
            }
        }
        
    
        
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success { 
            echo 'Hello Success'
        }
        failure { 
            echo 'Hello Failure'
        }
    }
}