pipeline {
    agent any

    environment{
        CI = 'true'
    }
    tools{
        nodejs "Node-16.14.0"
    }
    stages {
        stage('Build') {
            steps { 
                echo 'executing node..'
                sh 'npm install'
                echo 'executing yarn..'
                sh 'npm install yarn'
                echo 'finishing build..'
              
           }
        }
        stage('Test'){
            steps{
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Running'){
            steps{
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
