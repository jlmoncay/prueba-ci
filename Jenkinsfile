pipeline {
  agent {label 'controller'}
  stages {
    stage('build') {
      steps {
        echo "build stage"
        echo 'before setting export.sh'
        
        sh '''
        . /home/kevin/esp/esp-idf/export.sh
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