pipeline {
  agent {
    docker {
      image 'ubuntu:16.04'
    }

  }
  stages {
    stage('Clone repository') {
      steps {
        git(url: 'https://github.com/riyenas0925/Today_Develop.git', branch: 'develop', changelog: true, credentialsId: 'riyenas0925')
      }
    }

    stage('Clean') {
      steps {
        sh '''chmod +x mvnw
./mvnw clean'''
      }
    }

    stage('Build') {
      steps {
        sh './mvnw install'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "Deploy"'
      }
    }

  }
}