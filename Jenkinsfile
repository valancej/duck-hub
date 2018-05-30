pipeline {

    agent none

    stages {
        stage('Build') { 
            agent {docker 'maven:3.3.9'}
            steps {
                sh 'curl -O  https://blackducksoftware.github.io/hub-docker-inspector/hub-docker-inspector.sh && chmod +x hub-docker-inspector.sh'
                sh './hub-docker-inspector.sh --upload.bdio=false --docker.image=ubuntu'
                //sh 'mvn -B -DskipTests clean install'
                //sh "./hub-detect.sh --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true"
            }
        }
    }
}
