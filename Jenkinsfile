node('master') {

    stage('Checkout/Build/Test') {

        // Checkout files.
        checkout([
            $class: 'GitSCM',
            branches: [[name: 'master']],
            doGenerateSubmoduleConfigurations: false,
            extensions: [], submoduleCfg: [],
            userRemoteConfigs: [[
                name: 'github',
                url: 'https://github.com/Param592/JenkinTest.git'
            ]]
        ])

        // Build and Test
        sh 'xcodebuild -scheme "JenkinTest" -configuration "Debug" build test -destination "platform=iOS Simulator,name=iPhone 6,OS=12.1" -enableCodeCoverage YES | /usr/local/bin/xcpretty -r junit'

        // Publish test restults.
        step([$class: 'JUnitResultArchiver', allowEmptyResults: true, testResults: 'build/reports/junit.xml'])
    }

    stage('Analytics') {
        
        parallel Coverage: {
            // Generate Code Coverage report
            sh '/usr/local/bin/slather coverage --jenkins --html --scheme JenkinTest JenkinTest.xcodeproj/'
    
            // Publish coverage results
            publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'html', reportFiles: 'index.html', reportName: 'Coverage Report'])
        
            
        }, 
            //Checkstyle: {

            // Generate Checkstyle report
            //sh '/usr/local/bin/oclint -json-compilation-database -- -report-type pmd -o oclient.xml'
    
            // Publish checkstyle result
            //step([$class: 'PMD', canComputeNew: false, defaultEncoding: '', healthy: '', pattern: 'oclient.xml', unHealthy: ''])
        //}, 
        failFast: true|false   
    }

    stage ('Notify') {
        // Send slack notification
        //slackSend channel: '#my-team', message: 'JenkinTest - Successfully', teamDomain: 'my-team', token: 'my-token'
    }
}
