pipeline {
  agent any
  stages {
    stage('build') {
                  sh 'xcodebuild -scheme "JenkinTest" -configuration "Debug" build test -destination "platform=iOS Simulator,name=iPhone 6,OS=10.1" -enableCodeCoverage YES | /usr/local/bin/xcpretty -r junit'
      steps {
			$class: 'JUnitResultArchiver', allowEmptyResults: true, testResults: 'build/reports/junit.xml'	
      }
    }
  }
}
