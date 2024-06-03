pipeline {
  agent none
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh 'whoami'
      }
    }
    stage('test') {
        agent {label 'controller'}
        steps {
            echo "test stage"
            sh 'pwd'
        }
    }
    stage('deploy') {
        agent {label 'controller'}
        steps {
            echo "deploy stage"
            sh 'hostname -I'
        }
    }
  }
}
