
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      pomVersion = tkitpom.setVersion(POM_VERSION)
      
      tkitmajorVersion = pomVersion.getMajor()
      tkitminorVersion = pomVersion.getMinor()
      tkitpatchVersion = pomVersion.getPatch()
      tkitbuildVersion = pomVersion.getBuild()
      
      currentVersion = pomVersion.getCurrent()
      releaseVersion = pomVersion.getRelease()
      releaseIncVersion = pomVersion.increment(pomVersion.BUILD).getRelease()
   }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
 
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION ++ Version: $tkitmajorVersion - $tkitminorVersion - $tkitpatchVersion"
              echo "Current: $currentVersion -- RELEASE: $releaseVersion -- INC: $releaseIncVersion"
            }
      }
    }
   }
}
