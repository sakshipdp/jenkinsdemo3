pipeline {
    agent any
    environment {
        PYTHON = 'C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe'
    }
    stages {
        stage('checkout code') {
            steps{
                checkout scm
            }
        }
        stage('extract data') {
            steps{
                bat "${env.PYTHON} extract.py" 
            }
        }
        
    }
    post {
        success {
           echo "success...."
        }
        failure {
           echo "failure...."
        }
        always {
           echo "always...."
        }
    }
}