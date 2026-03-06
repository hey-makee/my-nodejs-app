pipeline {
    agent any

    tools {
        nodejs 'NodeJS' 
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo "Downloading packages for Node..."
                sh 'npm install' // Changed back to 'sh'
            }
        }
        stage('Test Application') {
            steps {
                echo "Running application tests..."
                sh 'npm test' // Changed back to 'sh'
            }
        }
    }
}
