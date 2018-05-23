pipeline {
    stages {
        stage('Build') { 
            agent {docker 'maven:3.3.9'}
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
