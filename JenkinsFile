pipeline {
    agent any

    tools {
        // Specify the Node.js version you set up in Global Tool Configuration
        nodejs 'NodeJS'
    }

    environment {
        NODE_ENV = 'production' // Example: Setting a Node.js environment variable
    }

    stages {
        stage('Install Dependencies') {
            steps {
                // Install npm dependencies
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests
                sh 'npm test'
            }
        }

        stage('Build Project') {
            steps {
                // Build the project
                sh 'npm run build'
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Archive build artifacts
                archiveArtifacts artifacts: 'build/**', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
