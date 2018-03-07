
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
      pomVersion = tkitpom.setVersion(POM_VERSION)
   }

  stages {

    stage('prepare release') {
      steps {
           maintainer '1000kit'
           script {
              echo '----- prepare release ------'
              tkitmajorVersion = pomVersion.getMajor()
              echo '----- GetMinor ------'
      		  tkitminorVersion = pomVersion.getMinor()
      		  echo '----- GetPatch ------'
      		  tkitpatchVersion = pomVersion.getPatch()
      		  echo '----- GetBuild ------'
      	 	  tkitbuildVersion = pomVersion.getBuild()
      
      			echo '----- GetCurrent ------'
      		  currentVersion = pomVersion.getCurrent()
      		  echo '----- GetRelease ------'
      		  releaseVersion = pomVersion.getRelease()
      		  echo '----- GetIncRelease ------'
      		  releaseIncVersion = pomVersion.increment(pomVersion.BUILD).getRelease()
              
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION ++ Version: $tkitmajorVersion - $tkitminorVersion - $tkitpatchVersion"
              echo "Current: $currentVersion -- RELEASE: $releaseVersion -- INC: $releaseIncVersion"
            }
      }
    }
   }
}
