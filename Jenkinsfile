pipeline {
    agent any
    environment {
        HOME = '/home/asif'
        PATH = "/home/asif/.sdkman/candidates/sbt/current/bin:${env.PATH}"
    }
    stages {
        stage('Compile') {
            steps {
                echo "Compile Project"
                sh "sbt compile"
            }
        }
    }
}
