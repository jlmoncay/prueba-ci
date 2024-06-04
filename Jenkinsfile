pipeline {
  agent {label 'controller'}
   environment {
       ESP_PATH = "/home/kevin/esp/esp-idf"
     }
  stages {
    stage('build') {
      steps {
        echo "build stage"
        echo 'before setting export.sh'
        
        sh '''
        #!/bin/bash
        cd "/${ESP_PATH}"
        
        . export.sh
        idf.py set-target esp32
        idf.py build
        '''
      
        echo 'after setting export.sh'
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