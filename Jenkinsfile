pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout from Git
                    git branch: 'main', url: 'https://github.com/AjayBanbare/Angular-App.git'
                }
            }
        }

        stage('Install node modules') {
            steps {
                script {
                    // Install Node.js modules
                    sh "npm install"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build Angular project
                    sh "npm run build"
                }
            }
        }

        stage('Deploy') {
            steps {
                // Copy Angular build artifacts to Jenkins server
                sh "rm -rf /var/www/html/*" // Clear the existing content
                sh "cp -r dist/* /var/www/html/" // Copy the build artifacts to the Apache web root
            }
        }
    }
}
