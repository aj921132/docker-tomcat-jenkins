pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'echo "hello ${CHROME_PATH} "'
          }
        }

        stage('parallel build') {
          steps {
            echo 'echo "build 2"'
          }
        }

        stage('test') {
          steps {
            writeFile(file: 'unittext', text: 'hello frm text')
          }
        }

      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            echo 'deploy stage'
            input(message: 'are u sure', id: '1')
          }
        }

        stage('archive') {
          steps {
            archiveArtifacts 'unittext'
          }
        }

      }
    }

  }
  environment {
    CHROME_PATH = 'c:/prgrm'
  }
}