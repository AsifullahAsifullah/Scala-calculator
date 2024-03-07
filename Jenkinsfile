pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build Image"
                sh 'chmod 755 /var/lib/jenkins/plugins/sbt"
                sh "/var/lib/jenkins/plugins/sbt compile"
            }
        }
    }
}
