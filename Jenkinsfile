pipeline {
  agent none
   environment {
       
        IDF_PATH = "/var/lib/jenkins/workspace/prueba-ci/esp/esp-idf"
        
    }
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh ". $IDF_PATH/export.sh"
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