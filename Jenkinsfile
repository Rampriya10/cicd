pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout code from GitHub repository
                git branch: 'main', url: 'https://github.com/Rampriya10/cicd.git'
            }
        }

        stage('Run Greeting Script') {
            steps {
                script {
                    // Run the greeting.sh script
                    sh '''#!/bin/bash
                    chmod +x greeting.sh  # Ensure the script is executable
                    ./greeting.sh         # Run the script
                    '''
                }
            }
        }

        stage('Post-Build Actions') {
            steps {
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

