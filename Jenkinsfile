
pipeline {
  agent any

  stages {
    stage('Static Analysis') {
      steps {
        echo "Running scapegoat"
        sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt scapegoat"
        // Use SBT plugin to run scapegoatCompile

                    // Check for warnings (modify condition if needed)
                    if (sh(returnStatus: true, script: 'sbt last exited :: 0').trim() != '0') {
                        error 'Scapegoat analysis found warnings. Fix them before proceeding.'
                    } else {
                        echo 'Scapegoat analysis successful (no warnings).'
                    }
      }
    }
  }
}
