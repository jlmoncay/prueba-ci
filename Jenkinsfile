pipeline {
  agent none
  stages {
    stage('build') {
        agent {
            docker { 
                image 'espressif/idf:v4.4.2' 
                args '-v /home/kevin/local-agents/new-local-agent/workspace/new-pipeline:/opt/esp/idf'
            }
        }
        steps {
            sh 'idf.py build'
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