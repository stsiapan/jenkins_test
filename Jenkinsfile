@Library('liba@master') _

pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    
    stage('get dockerfile') {
      steps {
        createDockerfile()
      }
    }
    
    stage('Log error') {
      steps {
        logError 'panic mode!'
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
