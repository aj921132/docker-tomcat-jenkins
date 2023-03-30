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
            echo 'deploy stage to dev'
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

    stage('production deploy') {
      steps {
        echo 'heelo from prod'
      }
    }

  }
  environment {
    CHROME_PATH = 'c:/prgrm'
  }
}