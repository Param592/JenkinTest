pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(bundleID: 'com.btor.JenkinTest', configuration: 'Debug', ipaExportMethod: 'development', manualSigning: true, xcodeSchema: 'JenkinTest', provisioningProfiles: [[provisioningProfileAppId:'com.btor.JenkinTest', provisioningProfileUUID:'8d50d73e-8533-42b0-908e-00126132a120']], buildIpa: true, ipaName: 'dev')
      }
    }
  }
}
