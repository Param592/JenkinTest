pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(bundleID: 'com.btor.JenkinTest', configuration: 'Debug', ipaExportMethod: 'Development', manualSigning: true, xcodeSchema: 'JenkinTest')
      }
    }
  }
}