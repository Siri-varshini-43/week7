
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t week7 .'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Docker container...'
                bat 'docker rm -f week7-app || exit /b 0'
                bat 'docker run --rm -d -p 5000:5000 --name week7-app week7'
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
        always {
            echo 'Jenkins pipeline execution completed.'
        }
    }
}
