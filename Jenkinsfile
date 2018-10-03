#!groovy

chuckNorris()

pipeline {
  agent any
  stages {
    stage('Build MTA') {
      steps {
        sh "/tools/buildMTASolution.sh ${params.userId}"
        archiveArtifacts artifacts: "${params.userId}-exercise.mtar"
      }
    }
    stage('Deploy to CF') {
      steps {
        sh "/tools/deployToCF.sh ${params.userId}"
      }
    }
  }
}
