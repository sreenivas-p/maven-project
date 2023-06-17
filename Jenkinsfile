pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                sucess {
                    echo 'Now Arching'
                    archiveArtifacts artifacts: '**/*.war'
                }
                
            }
        }
    }
}
