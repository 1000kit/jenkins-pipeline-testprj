
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
  	echo '----- Start Environment ------'
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      echo '----- POMVERSION ------'
      pomVersion = tkitpom.readVersion("pom.xml")
      echo '----- tkpitpom.readVersion ------'
      tkitmajorVersion = pomVersion.getMajor()
       echo '----- getMajora ------'
      tkitminorVersion = pomVersion.getMinor()
      echo '----- getMinor ------'
      tkitpatchVersion = pomVersion.getPatch()
      echo '----- getPatch ------'
      tkitbuildVersion = pomVersion.getBuild()
      echo '----- getbuild ------'
      
      currentVersion = pomVersion.getCurrent()
      echo '----- getCurrent ------'
      releaseVersion = pomVersion.getRelease()
      echo '----- getRelease ------'
      releaseIncVersion = pomVersion.increment(pomVersion.BUILD).getRelease()
      echo '----- getReleaseInc ------'
  }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
              echo '----- prepare release ------'
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION ++ Version: $tkitmajorVersion - $tkitminorVersion - $tkitpatchVersion"
              echo "Current: $currentVersion -- RELEASE: $releaseVersion -- INC: $releaseIncVersion"
            }
      }
    }
   }
}
