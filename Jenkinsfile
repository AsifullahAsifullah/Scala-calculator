pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build Image"
                sh "/var/lib/jenkins/plugins/sbt/WEB-INF/lib/sbt.jar  buildDockerImage"
            }
        }
    }
}
