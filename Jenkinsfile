pipeline {
  agent none
  stages {
    stage('build') {
        agent {label 'lagent1'}
        steps {
          sh 'docker run --rm -v $WORKSPACE:/project -w /project espressif/idf:v4.4.2 idf.py build'
          stash name: "build-binaries", includes: "build/**/ *, sdkconfig"
        }
    }

    stage('tarea-agente1') {
        agent {label 'agent1'}
        steps {
            dir("build-binaries") {
                unstash "build-binaries"
            }
            sh 'echo Antes de almacenar los archivos'
            
            sh 'echo Archivos almacenados con éxito'
        }
    }
  }
}