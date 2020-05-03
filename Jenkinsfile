pipeline {
  agent any
  stages {
    stage ('Test') {
      steps {
        script {
          if (isUnix()) {
            sh "gradle clean test"
          }
          else {
            bat "gradle clean test"
          }
        }
        junit "build/test-results/test/*.xml"
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: "build/libs/*.war"
    }
  }
}