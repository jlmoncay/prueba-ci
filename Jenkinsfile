pipeline {
  agent none
  stages {
    stage('build') {
        agent {label 'lagent1'}
        steps {
          sh 'docker run --rm -v $WORKSPACE:/project -w /project espressif/idf:v4.4.2 idf.py build'
          stash name: "build-binaries", includes: "build/bootloader/*.bin, build/partition_table/*.bin, build/*.bin"
        }
    }

    stage('tarea-agente1') {
        agent {label 'rbagent'}
        options { skipDefaultCheckout() }
        steps {
            unstash "build-binaries"
            
        }
    }

    stage('load-bin-and-test-rbagent1') {
        agent {label 'rbagent'}
        options { skipDefaultCheckout() }
        steps {
            sh 'echo load binaries to do something on the raspberry pi'
        }
        post {
            success {
                sh 'echo Running tests'
            }
        }
    }
  }
}