
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      version = tkitpom.version("pom.xml")
      tkitmajorVersion =  tkitpom.majorVersion("pom.xml")
      tkitminorVersion =  tkitpom.minorVersion("pom.xml")
      tkitpatchVersion =  tkitpom.patchVersion("pom.xml")
      tkitbuildVersion =  tkitpom.buildVersion("pom.xml")
  }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
              echo '----- prepare release ------'
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION ++ Version: $tkitmajorVersion - $tkitminorVersion - $tkitpatchVersion - $tkitbuildVersion"
            }
      }
    }
   }
}
