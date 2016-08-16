stage "Build"
checkout scm

sh 'mvn compile'

stage "Test"
node {
    sauce('f0a6b8ad-ce30-4cba-bf9a-95afbc470a8a') {
        sauceconnect(options: '', useGeneratedTunnelIdentifier: true, verboseLogging: true) {
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@ondemand.saucelabs.com:80/wd/hub -Dbrowser=firefox'
        }
    }
}
