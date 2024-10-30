pipeline {
    agent any  // Use any available agent/node

    triggers {
        pollSCM('* * * * *') // Poll the repository every minute for changes
    }

    environment {
        BUILD_SCRIPT = './build.sh'  // Path to your build script
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-repository-url.git'
            }
        }

        stage('Build') {
            steps {
                sh "${BUILD_SCRIPT}"  // Execute the build script
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                // Add test execution scripts if needed
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
                // Include deployment steps here if required
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
