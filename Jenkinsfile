pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }

      }
    }

    stage('Result') {
      steps {
        realtimeJUnit(testResults: '**/target/surefire-report/TI')
        archiveArtifacts 'target/*.jar'
      }
    }

  }
  environment {
    label = 'master'
  }
}