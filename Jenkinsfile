
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      version = tkitpom.version("pom.xml")
      majorVersion =  tkitpom.majorVersion("pom.xml")
      minorVersion =  tkitpom.minorVersion("pom.xml")
      patchVersion =  tkitpom.patchVersion("pom.xml")
      buildVersion =  tkitpom.buildVersion("pom.xml")
  }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
              echo '----- prepare release ------'
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION"
              echo "Version: $majorVersion - $minorVersion - $patchVersion - $buildVersion"
            }
      }
    }
   }
}
