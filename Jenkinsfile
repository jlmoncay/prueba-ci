pipeline {
  agent none
   environment {
       
        IDF_PATH = "/home/kevin/esp/esp-idf"
        
    }
  stages {
    stage('build') {
      agent {label 'controller'}
      steps {
        echo "build stage"
        sh "chmod +x /home/kevin/esp/esp-idf/export.sh"
        sh '. $IDF_PATH/export.sh'
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
