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

        stage('') {
          steps {
            echo 'echo "build 2"'
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