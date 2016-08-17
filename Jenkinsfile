node {
    stage "Build"
    checkout scm

    sh 'mvn compile'


    stage "Test"
    sauce('f0a6b8ad-ce30-4cba-bf9a-95afbc470a8a') {
        sauceconnect(options: '', useGeneratedTunnelIdentifier: true, verboseLogging: true) {
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@ondemand.saucelabs.com:4445/wd/hub -Dbrowser=firefox'
        }
    }
}
