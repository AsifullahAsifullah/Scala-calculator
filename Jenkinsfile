pipeline {
    agent any
    
    stages {
        stage('Compiling') {
            steps {
                echo "Running Project"
                sh "sudo /var/lib/jenkins/plugins/sbt/WEB-INF/lib/sbt.jar compile"
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
}
