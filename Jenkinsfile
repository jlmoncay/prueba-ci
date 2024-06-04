pipeline {
  agent {label 'controller'}
  stages {
    stage('build') {
      steps {
        echo "build stage"
        sh '''
        /home/kevin/Escritorio/hello.sh
        '''



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