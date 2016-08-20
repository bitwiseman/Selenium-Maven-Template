node {
    stage "Build"
    //deleteDir()
    checkout scm

    sh 'mvn compile'

    stage "Test"
    sauce('82f8f013-e519-486a-b1f6-84bb0c658ee1') {
        sauceconnect(options: '', useGeneratedTunnelIdentifier: true, verboseLogging: true) {

            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=vista -Dbrowser=safari -DbrowserVersion=5.1'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=mavericks -Dbrowser=safari -DbrowserVersion=7.0'

            // sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=win7 -Dbrowser=firefox -DbrowserVersion=48'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=win8 -Dbrowser=firefox -DbrowserVersion=48'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=win10 -Dbrowser=firefox -DbrowserVersion=48'

            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=yosemite -Dbrowser=firefox -DbrowserVersion=48'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=yosemite -Dbrowser=firefox -DbrowserVersion=47'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=yosemite -Dbrowser=firefox -DbrowserVersion=46'
            sh 'mvn verify -Dremote=true -DseleniumGridURL=http://${SAUCE_USERNAME}:${SAUCE_ACCESS_KEY}@localhost:${SELENIUM_PORT}/wd/hub -DtunnelIdentifier=${TUNNEL_IDENTIFIER} -Dplatform=yosemite -Dbrowser=firefox -DbrowserVersion=45'
        }
    }
}
