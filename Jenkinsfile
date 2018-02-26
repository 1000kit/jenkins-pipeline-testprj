
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      pomVersion = tkitpom.version("pom.xml")
      tkitmajorVersion = pomVersion.getMajor()
      tkitminorVersion = pomVersion.getMinor()
      tkitpatchVersion = pomVersion.getPatch()
      tkitbuildVersion = pomVersion.getBuild()
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
