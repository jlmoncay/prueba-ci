pipeline {
  agent none
   environment {
       
        IDF_PATH = "$HOME/esp/esp-idf"
        
    }
  stages {
    stage('build') {
      steps {
        echo "build stage"
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
