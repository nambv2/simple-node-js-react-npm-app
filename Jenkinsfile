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
              sh '''  
              #   #!/bin/bash
                    VERSION=$(node -p "require('./package.json').version")
                    if [[ "$VERSION" == *"-SNAPSHOT"* ]]; then
                    echo "Deploying snapshot to Nexus snapshot repository..."
                    npm adduser --auth-type=legacy --registry=$(node -p "require('./package.json').publishConfig.registry")
                    npm publish --registry=$(node -p "require('./package.json').publishConfig.registry")
                    else
                        echo "Deploying release to Nexus release repository..."
                    npm adduser --auth-type=legacy --registry=$(node -p "require('./package.json').releasePublishConfig.registry")
                    npm publish --registry=$(node -p "require('./package.json').releasePublishConfig.registry")
                    fi
                '''
            }
        }
    }
}
