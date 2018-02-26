
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any

  environment {
      POM_VERSION = readMavenPom(file: 'pom.xml').getVersion()
  }

  stages {

    stage('prepare release') {
      steps {
           script {
              echo '----- prepare release ------'
              sh ' pwd ; ls -la '
              echo "POM_VERSION: $POM_VERSION"
              version = tkitpom.version('pom.xml')
              majorVersion =  tkitpom.majorVersion('pom.xml')
              minorVersion =  tkitpom.minorVersion('pom.xml')
              patchVersion =  tkitpom.patchVersion('pom.xml')
              buildVersion =  tkitpom.buildVersion('pom.xml')

              echo "Version: $majorVersion - $minorVersion - $patchVersion - $buildVersion"
            }
      }
    }
   }
}
