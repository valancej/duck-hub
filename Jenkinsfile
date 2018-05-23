pipeline {

    agent none

    stages {
        stage('Build') { 
            agent {docker 'maven:3.3.9'}
            steps {
                sh 'mvn -B -DskipTests clean package'
		bash '<(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true' 
            }
        }
    }
}
