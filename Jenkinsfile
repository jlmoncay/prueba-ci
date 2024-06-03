pipeline {
  agent none
  environment {
        HOME = '/home/kevin'
        IDF_PATH = "$HOME/esp/esp-idf"
    }
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh "sudo . $IDF_PATH/esp/esp-idf/export.sh"
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