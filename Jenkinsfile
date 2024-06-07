pipeline {
  agent none
  environment {
    IDF_PATH = '/opt/esp/idf'
  }
  stages {
    stage('build') {
        agent {
            docker { 
                image 'espressif/idf:release-v4.3' 
                
            }
        }
        steps {
            sh '''
                . $IDF_PATH/export.sh
                idf.py set-target esp32
                idf.py build
            '''
        }
    }
    stage('test') {
        agent {label 'lagent1'}
        steps {
            echo "test stage"
        }
    }
    stage('deploy') {
        agent {label 'lagent1'}
        steps {
            echo "deploy stage"
        }
    }
  }
}