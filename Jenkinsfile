pipeline {
  agent none
  environment {
        IDF_PATH = '/home/kevin/local-agents/workspace/new-pipeline/project-cache/idf'
  }
  stages {
    stage('build') {
        agent {
            docker { 
                image 'espressif/idf:v4.4.2'
                args '-v /home/kevin/local-agents/workspace/new-pipeline/project-cache:/opt/esp'
            }
        }
        steps {
            sh '''
                . ${IDF_PATH}/export.sh
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