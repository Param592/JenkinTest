pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(buildIpa: true, ipaName: 'Test', bundleID: 'com.btor.JenkinTest', configuration: 'Debug', xcodeSchema: 'JenkinTest', ipaExportMethod: 'development', provisioningProfiles: [[provisioningProfileAppId:'com.btor.JenkinTest', provisioningProfileUUID:'1aff35f0-30ee-473d-bad6-534d4ab28e4c']], manualSigning: true)
      }
    }
  }
}