pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from GitHub
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], 
                          userRemoteConfigs: [[url: 'https://github.com/AnaDob/myDevOpsapp.git']]])
            }
        }
        
        stage('Build') {
            steps {
                // Build the app by executing bin/lavagna.sh
                sh 'chmod +x bin/lavagna.sh'
                sh 'bin/lavagna.sh'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests using Maven (you can replace this with your test command)
                sh 'mvn test'
            }
        }
    }
    
    post {
        always {
            // Clean up steps if necessary
            echo 'Performing cleanup...'
        }
        success {
            // Actions to perform when the pipeline succeeds
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to perform when the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}
