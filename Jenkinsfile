pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(bundleID: 'com.btor.JenkinTest', configuration: 'Debug', ipaExportMethod: 'Development', manualSigning: true, xcodeSchema: 'JenkinTest', provisioningProfiles:[[provisioningProfileAppId:'com.btor.JenkinTest', provisioningProfileUUID:'1aff35f0-30ee-473d-bad6-534d4ab28e4c']])
      }
    }
  }
}
