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

        stage('log') {
          steps {
            writeFile(file: 'logfile.txt', text: 'this is a log file')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy', id: 'yes', ok: 'Continue')
            writeFile(file: 'logfile.txt', text: 'This contains all the logs')
          }
        }

        stage('logfile') {
          steps {
            archiveArtifacts 'logfile.txt'
          }
        }

      }
    }

  }
}