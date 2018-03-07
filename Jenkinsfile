
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()     
      //releaseIncVersion = tkitpom.incrementRelease(POM_VERSION, 3)
   }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
 
              sh ' pwd ; ls -la '
              echo "INC: $releaseIncVersion"
            }
      }
    }
   }
}
