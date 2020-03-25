@Library('liba@master') _

pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    
    stage('ls') {
      steps {
        sh 'ls -la; pwd'
      }
    }
    
    stage('Build') {
      steps {
        dockerCmd 'version'
        dockerCmd 'build -t ealebed/hellonode:latest .'
        dockerCmd 'image ls'
      }
    }
  }
}
