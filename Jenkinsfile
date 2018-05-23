pipeline {

    agent none

    stages {
        stage('Build') { 
            agent {docker 'maven:3.3.9'}
            steps {
                sh 'curl -O https://blackducksoftware.github.io/hub-detect/hub-detect.sh && chmod +x hub-detect.sh'
                sh 'mvn -B -DskipTests clean package'
                sh "./hub-detect.sh --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true"
            }
        }
    }
}
