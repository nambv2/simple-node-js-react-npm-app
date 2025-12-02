pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        // stage('Test') { 
        //     steps {
        //         sh './jenkins/scripts/test.sh' 
        //     }
        // }
         stage('Push to nexus') {
            steps {
              // withCredentials([string(credentialsId: 'NPM_TOKEN_ID', variable: 'NPM_TOKEN')]) {
              //   sh 'npm config set //registry.npmjs.org/:_authToken ${NPM_TOKEN}' // Or your private registry URL
              //   sh 'npm install'
              
              //    }
            //   sh '''
                                
                           
            //     '''
            sh './jenkins/scripts/detect.sh' 
            }
        }
    }
}
