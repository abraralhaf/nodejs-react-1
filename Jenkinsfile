pipeline {
    agent any
    stages {
        stage('Build') {
            steps { 
                echo 'executing node..'
                nodejs('Node-16.14.0'){
                    sh 'npm install'
                    sh 'yarn install'
                }
           }
        }
    }
}
