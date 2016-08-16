stage "Build"

stage "Test"
node {
    sauce('f0a6b8ad-ce30-4cba-bf9a-95afbc470a8a') {
        sauceconnect(options: '', useGeneratedTunnelIdentifier: true, verboseLogging: true) {
            checkout scm
        }
    }
}
