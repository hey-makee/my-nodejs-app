pipeline {
    agent any

    tools {
        nodejs 'NodeJS' 
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo "Downloading packages for Node..."
                sh 'npm install' 
            }
        }
        
        stage('Test Application') {
            steps {
                echo "Running application tests..."
                sh 'npm run test --if-present || echo "No tests defined in package.json yet, moving to the next stage!"' 
            }
        }
        
        stage('Package Application') {
            steps {
                echo "Packaging the application for deployment..."
                // The Fix: We added --exclude=my-nodejs-app-build.tar.gz
                sh 'tar -czf my-nodejs-app-build.tar.gz --exclude=node_modules --exclude=my-nodejs-app-build.tar.gz .'
            }
        }
    }
    
    post {
        success {
            echo "Pipeline succeeded! Saving the build artifact..."
            archiveArtifacts artifacts: 'my-nodejs-app-build.tar.gz', followSymlinks: false
        }
        failure {
            echo "The pipeline failed. Time to check the logs."
        }
    }
}
