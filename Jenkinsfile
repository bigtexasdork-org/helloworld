#!groovy 

node {
  stage ('Checkout') {
    checkout scm
  }

  stage ('Setup') {
    sh 'npm install'
  }

  stage ('Mocha test') {
    sh './node_modules/mocha/bin/mocha --exit'
  }

  stage ('Cleanup') {
    echo 'prune and cleanup'
    sh 'npm prune'
    sh 'rm node_modules -rf'
  }
}
