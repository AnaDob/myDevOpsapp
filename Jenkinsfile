pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    def repositoryUrl = 'https://github.com/AnaDob/myDevOpsapp.git'
                    def repoDir = 'myDevOpsapp'
                    
                    // Clean up existing directory
                    deleteDir()
                    
                    // Clone the repository
                    git url: repositoryUrl, branch: 'main', directory: repoDir
                }
            }
        }
        
        stage('Build and Execute') {
            steps {
                dir("${repoDir}/main/bin") {
                    script {
                        // Execute the lavagna.sh script
                        sh './lavagna.sh'
                    }
                }
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            cleanWs()
        }
    }
}
