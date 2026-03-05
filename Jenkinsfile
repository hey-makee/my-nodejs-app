pipeline {
    agent any

    tools {
        // This tells Jenkins to grab the Node tool we set up in Step 1
        nodejs 'NodeJS' 
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo "Downloading packages for Node..."
                // For Windows machines, change 'sh' to 'bat'
                bat 'npm install' 
            }
        }
        stage('Test Application') {
            steps {  
                echo "Running application tests..."
                // This runs the test script inside your package.json
                bat 'npm test' 
            }
        }
    }
}
