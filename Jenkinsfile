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
                echo 'Running tests...'
                
                    bat 'docker run --rm -d -p 5000:5000 --name week7-app week7'
                    
                
            }
        }
        post {
            success {
                echo 'Tests passed!'
            }
            failure {
                echo 'Tests failed!'
            }
        }
        
    }
}