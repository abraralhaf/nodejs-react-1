pipeline {
    agent any

    environment{
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps { 
                echo 'executing node..'
                nodejs('Node-16.14.0'){
                    sh 'npm install'
                    sh 'npm install yarn'
                }
           }
        }
        stage('Test'){
            steps{
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
