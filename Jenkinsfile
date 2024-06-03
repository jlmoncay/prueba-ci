pipeline {
  agent none
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh 'whoami'
        sh 'pwd'
        echo 'before setting export.sh'
        sh ". /home/kevin/esp/esp-idf/export.sh"
        echo 'after setting export.sh'
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