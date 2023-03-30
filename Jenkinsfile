pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'echo "hello "'
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
      steps {
        echo 'deploy stage'
        input(message: 'are u sure', id: '1')
      }
    }

  }
}