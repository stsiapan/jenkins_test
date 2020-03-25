@Library('liba@master')

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
        script {
          sh '''
            dockerCmd version
            dockerCmd build -t ealebed/hellonode:latest .
            dockerCmd image ls
            
          '''
        }
      }
    }
  }
}
