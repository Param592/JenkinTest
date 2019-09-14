pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        xcodeBuild(buildIpa: true, ipaName: 'Test', bundleID: 'com.btor.JenkinTest')
      }
    }
  }
}