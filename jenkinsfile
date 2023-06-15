pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    
    post {
        success {
                echo 'now archving'
                archiveArtifacts artifacts: '**/target/*.war'
        }
        
        failure {
            // Perform actions on build failure
            // For example, sending notifications or cleaning up resources
            echo 'Build failed! Sending notification...'
            // Add code for sending notifications here
        }
    }
}
