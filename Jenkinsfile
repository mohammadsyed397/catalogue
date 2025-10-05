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
        stage('Read package Version') {
            steps {
                script{
                    def packageJson = readJSON file: 'package.json'
                    appVersion = packageJson.version
                    echo "Package version: ${appVersion}"
                }
            }
        }
        stage('install dependencies') {
            steps {
                script{
                    sh """
                       npm install
                    """
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