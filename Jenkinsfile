pipeline {
  agent none
  stages {
    stage('build') {
        agent {label 'lagent1'}
        steps {
          sh 'docker run --rm -v $WORKSPACE:/project -w /project espressif/idf:v4.4.2 idf.py build'
        }
    }

    stage('tarea-agente1') {
        agent {label 'agent1'}
        steps {
            sh 'whoami'
        }
    }
  }
}