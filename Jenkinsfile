
@Library('jenkins-pipeline-lib') _

pipeline {
  agent any


  stages {

    stage('prepare release') {
      steps {
           script {
              echo '----- prepare release ------'
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
