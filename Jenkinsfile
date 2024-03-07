pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo "Compile Project"
                sh "${tool name: 'sbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt  compile"
            }
        }
    }
}
