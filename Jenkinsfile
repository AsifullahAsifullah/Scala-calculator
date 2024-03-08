pipeline {
    agent any

    stages {
        stage('Static Analysis') {
            steps {
                echo "Running scapegoat"
                sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"
            }
        }
    }
    post {
        always {
            // Archive the Scapegoat report
            archiveArtifacts artifacts: '**/target/scala-2.13/scapegoat-report/scapegoat-scalastyle.xml'
            // Parse the Scapegoat report and fail the build if there are any warnings
            recordIssues(
                tools: [scapegoat(pattern: '**/target/scala-2.13/scapegoat-report/scapegoat-scalastyle.xml')],
                thresholdLimit: 'high',
                healthy: '',
                unhealthy: '100'
            )
        }
}
}
