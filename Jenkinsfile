pipeline {
  agent none
  stages {
    stage('build') {
        agent {
            docker { image 'espressif/idf:v4.4.2' }
        }
        steps {
            sh '''
            #!/bin/bash
            . $HOME/esp/esp-idf/export.sh
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