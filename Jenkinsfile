pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building Jenkins pipeline'
            echo 'Another build job'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the script'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy', id: 'yes', ok: 'no')
      }
    }

  }
}