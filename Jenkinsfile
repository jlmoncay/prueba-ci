pipeline {
  agent {label 'controller'}
  stages {
    stage('build') {
      steps {
        echo "build stage"
        sh '''
        #!/bin/bash

        echo Hello World
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