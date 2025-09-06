pipeline {
  agent any
  options { timestamps() }
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        sh 'echo "Build step (replace with your build tool)"'
      }
    }
    stage('Test') {
      steps {
        sh 'echo "Run tests here (pytest/mvn/gradle/etc.)"'
      }
    }
    stage('Archive') {
      steps {
        sh 'mkdir -p build && echo "artifact" > build/sample.txt'
        archiveArtifacts artifacts: 'build/**', fingerprint: true
      }
    }
  }
  post {
    always {
      junit allowEmptyResults: true, testResults: '**/test-results/*.xml'
      echo 'Pipeline completed.'
    }
  }
}
