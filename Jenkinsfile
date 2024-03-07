pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                echo "Compile Project"
                sh "/home/asif/.sdkman/candidates/sbt/current/bin/sbt compile"
            }
        }
    }
}
