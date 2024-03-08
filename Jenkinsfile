
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
        sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt docker:publishLocal"
        // script {
        //   def scapegoatOutput = sh(script: "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat", returnStdout: true).trim()
        //   // Check if scapegoat output contains the warning string
        //   if (scapegoatOutput.contains("[warn]")) {
        //     error "Scapegoat found issues. Failing the build."
        //   }
        // }
      }
    }
  }
}


