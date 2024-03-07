pipeline {
    agent any

//     environment {
//      SBT_HOME="${tool 'sbt'}"
//      PATH="${env.SBT_HOME}/bin:${env.PATH}"
// }
    stages {
        stage('Compiling') {
            steps {
                echo "Running Project"
                sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt compile"
            }
        }
        
        // stage('Running') {
        //     steps {
        //         echo "Running Project"
        //         sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt run"
        //     }
        // }

        // stage('Runing') {
        //     steps {
        //         echo "Runing Project"
        //         sh "sudo /home/asif/.sdkman/candidates/sbt/current/bin/sbt run"
        //     }
        // }
        
    }

    post {
        always {
            // Archive Scapegoat reports
            archiveArtifacts artifacts: '**/scapegoat.xml'
        }
        success {
            echo "Build successful"
        }
        failure {
            echo "Build failed due to Scapegoat errors or warnings"
            currentBuild.result = 'FAILURE'
        }
    }
}
