
// pipeline {
//   agent any

//   stages {
//     stage('Static Analysis') {
//       steps {
//         echo "Running scapegoat"
//         sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"
//       }
//     }
//   }
//   post {
//         always {
//             junit '/var/lib/jenkins/workspace/calculator/target/scala-2.13/scapegoat-report/scapegoat.xml'
//         }
//         failure {
//             echo 'Failed With Warning'
//         }
//     }
// }


pipeline {
  agent any

  stages {
    stage('Static Analysis') {
      steps {
        echo "Running scapegoat"
        script {
          def scapegoatOutput = sh(script: "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat", returnStdout: true).trim()
          // Check if scapegoat output contains any errors or warnings
          if (scapegoatOutput.contains("warn") || scapegoatOutput.contains("error")) {
            error "Scapegoat found issues. Failing the build."
          }
        }
      }
    }
  }
}
