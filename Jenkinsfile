pipeline {
  agent none
  stages {
    stage('build') {
      steps {
        echo "build stage"
        sh 'whoami'
      }
    }
    stage('test') {
        steps {
            echo "test stage"
            sh 'pwd'
        }
    }
    stage('deploy') {
        steps {
            echo "deploy stage"
            sh 'hostname -I'
        }
    }
  }
}