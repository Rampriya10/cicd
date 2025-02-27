pipeline {
    agent any  // Runs on any available agent

    environment {
        // Define any environment variables if needed (optional)
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout code from GitHub repository
                git branch: 'main', url: 'https://github.com/Rampriya10/cicd.git'

            }
        }

        stage('Run Greeting Script') {
            steps {
                // Run your greeting.sh script to print the greeting
                script {
                    // Execute the shell script 'greeting.sh' inside the repo
                    sh '''#!/bin/bash
                    chmod +x greeting.sh  # Make the script executable (if not already)
                    ./greeting.sh         # Run the script
                    '''
                }
            }
        }

        stage('Post-Build Actions') {
            steps {
                // You can add additional steps like archiving or notifications here if needed
                echo "Post-build actions can go here!"
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
