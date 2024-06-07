pipeline {
  agent none
  environment {
    IDF_PATH = '/opt/esp'
  }
  stages {
    stage('build') {
        agent {
            docker { 
                image 'espressif/idf:latest'
            }
        }
        steps {
            sh '''
                ${IDF_PATH}/entrypoint.sh
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