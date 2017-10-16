pipeline {
  agent any
  stages {
    stage('build group') {
      parallel {
        stage('build') {
          steps {
            echo 'step 1'
            bat 'package -Dmaven.test.skip=true'
          }
        }
        stage('message') {
          steps {
            bat 'maven -version'
          }
        }
      }
    }
    stage('post') {
      steps {
        cleanWs(cleanWhenFailure: true)
      }
    }
  }
}