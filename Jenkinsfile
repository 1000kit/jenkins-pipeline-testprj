
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      def pomVersion = tkitpom.version("pom.xml")
      def tkitmajorVersion = pomVersion.getMajor
      def tkitminorVersion = pomVersion.getMinor
      def tkitpatchVersion = pomVersion.getPatch
      def tkitbuildVersion = pomVersion.getBuild
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
