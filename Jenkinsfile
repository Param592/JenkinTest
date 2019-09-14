pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(buildIpa: true, generateArchive: true, ipaName: 'Test', manualSigning: true)
      }
    }
  }
}