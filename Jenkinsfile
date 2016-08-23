node {
    stage "Build"
    sh 'rm -rf target/failsafe-reports'

    checkout scm

    sh 'mvn compile'

    stage "Test"
    sauce('82f8f013-e519-486a-b1f6-84bb0c658ee1') {
        sauceconnect(options: '', useGeneratedTunnelIdentifier: true, verboseLogging: true) {
            def baseCommand = 'mvn verify -Dmaven.test.failure.ignore=true -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER}'
            sh baseCommand + ' -Dplatform=vista -Dbrowser=safari -DbrowserVersion=5.1'
            sh baseCommand + ' -Dplatform=mavericks -Dbrowser=safari -DbrowserVersion=7.0'

            sh baseCommand + ' -Dplatform=win7 -Dbrowser=firefox -DbrowserVersion=48'
            // sh baseCommand + ' -Dplatform=win8 -Dbrowser=firefox -DbrowserVersion=48'
            // sh baseCommand + ' -Dplatform=win10 -Dbrowser=firefox -DbrowserVersion=48'
            //
            // sh baseCommand + ' -Dplatform=mac -Dbrowser=firefox -DbrowserVersion=48'
            // sh baseCommand + ' -Dplatform=mac -Dbrowser=firefox -DbrowserVersion=47'
            // sh baseCommand + ' -Dplatform=mac -Dbrowser=firefox -DbrowserVersion=46'
            // sh baseCommand + ' -Dplatform=mac -Dbrowser=firefox -DbrowserVersion=45'

            archiveArtifacts '**/target/failsafe-reports/TEST-*.xml'
            junit '**/target/failsafe-reports/TEST-*.xml'

            step([$class: 'SauceOnDemandTestPublisher'])
        }
    }
}
