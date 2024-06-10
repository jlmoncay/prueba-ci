pipeline {
  agent none
  stages {
    stage('build') {
        agent {label 'lagent1'}
        steps {
          sh 'docker run --rm -v $WORKSPACE:/project -w /project espressif/idf:v4.4.2 idf.py build'
          archiveArtifacts artifacts: 'build/*, sdkconfig', allowEmptyArchive: true, onlyIfSuccessful: true
        }
    }

    stage('tarea-agente1') {
        agent {label 'agent1'}
        steps {
            sh 'echo Antes de copiar los archivos'
            copyArtifacts projectName: 'new-pipeline', selector: lastSuccessful(), filter: 'build/**, sdkconfig', target: 'archivos-copiados/'
            sh 'echo Archivos copiados con éxito'
            sh 'ls -l archivos-copiados/'
        }
    }
  }
}