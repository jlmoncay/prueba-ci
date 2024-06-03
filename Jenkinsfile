pipeline {
  agent none
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh 'get_idf'
        sh 'idf.py set-target esp32'
        sh 'idf.py build'
      }
    }
    stage('test') {
        steps {
            echo "test stage"
        }
    }
    stage('deploy') {
        steps {
            echo "deploy stage"
        }
    }
  }
}