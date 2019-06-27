#!groovy 

pipeline {
  agent any
  options {
    ansiColor('xterm')
  }
  
  stages {
    stage ('Checkout') {
      steps {
        checkout scm
      }
    }

    stage ('Setup') {
      steps {
        sh 'npm install'
      }
    }

    stage ('Mocha test') {
      steps {
        sh './node_modules/mocha/bin/mocha --exit'
      }
    }

    stage ('Cleanup') {
      steps {
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
      }
    }
  }
}