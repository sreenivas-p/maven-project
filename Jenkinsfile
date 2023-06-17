pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                build job: 'build-artifact'
            }
        }
            
        stage ('Deploy to Staging'){
            steps {
                build job: 'build-staging'
            }
        }

        stage ('Deploy to Production'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve PRODUCTION Deployment?'
                }

                build job: 'build-prod'
            }
            post {
                success {
                    echo 'Code deployed to Production.'
                }

                failure {
                    echo ' Deployment failed.'
                }
            }
        }


    }
}
