pipeline {
  agent any
  stages {
    stage('Clone Repository') {
      steps {
        checkout scm
      }
    }

    stage('Build') {
      steps {
        withMaven() {
          sh 'mvn clean verify'
        }

      }
    }

    stage('Build and Run') {
      steps {
        script {
          sh 'bin/lavagna.sh'

        }

      }
    }

  }
}