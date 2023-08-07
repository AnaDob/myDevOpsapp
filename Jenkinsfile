pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                deleteDir()
                checkout scm
            }
        }

        stage ('Build') {
            steps {
                withMaven {
                    sh "mvn clean verify"
                }
            }
        }

        stage('Build and Run') {
            steps {
                script {
                    sh 'mvn clean package'
                    sh 'bin/lavagna.sh'
                }
            }
        }
    }
}

