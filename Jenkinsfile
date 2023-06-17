pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                build job: 'build-package-archive'
            }
        }
        stage ('Deploy to Staging'){
            steps {
                build job: 'deploy-staging'
            }
        }
        
    }
}
