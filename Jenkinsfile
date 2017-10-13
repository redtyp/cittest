pipeline {
  agent any
  stages {
    stage('build group') {
      parallel {
        stage('build') {
          steps {
            echo 'step 1'
            mail(subject: 'step 1 done', body: 'hi,step 1 was done', to: 'dawei.yuan@cfgdc.ne')
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