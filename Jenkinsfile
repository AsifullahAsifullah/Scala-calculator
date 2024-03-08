
pipeline {
  agent any

  stages {
    stage('Static Analysis') {
      steps {
        echo "Running scapegoat"
        sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"
        // script {
        //             // Use SBT plugin to run scapegoatCompile
        //              sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"

        //             // Check for warnings (modify condition if needed)
        //             if (sh(returnStatus: true, script: 'sbt last exited :: 0') != '0') {
        //                 error 'Scapegoat analysis found warnings. Fix them before proceeding.'
        //             } else {
        //                 echo 'Scapegoat analysis successful (no warnings).'
        //             }
        //         }
      }
    }
  }
  post {
        always {
            junit '/var/lib/jenkins/workspace/calculator/target/scala-2.13/scapegoat-report/scapegoat.xml'
        }
        failure {
            echo 'Failed With Warning'
        }
    }
}
