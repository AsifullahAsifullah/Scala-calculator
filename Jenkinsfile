
pipeline {
  agent any

  stages {
    stage('Static Analysis') {
      steps {
        echo "Running scapegoat"
        sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"
        recordIssues(
          tools: [scapegoat(pattern: 'target/scala-2.13/scapegoat-report/scapegoat-scalastyle.xml')]
        )
      }
    }
  }
}
