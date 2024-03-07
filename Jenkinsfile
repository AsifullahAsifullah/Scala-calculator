pipeline {
    agent any
    
 tools {
        sbt 'sbt'
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
