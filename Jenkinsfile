pipeline {
    agent any
    environment {
        PYTHON = 'C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe'
    }
    triggers {
         cron("*/2 * * * *")
    }
    stages {
        stage('checkout code') {
            steps{
                checkout scm
            }
        }
        stage('extract data') {
            steps{
                bat "${env.PYTHON} extract_data.py" 
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




// node {
//     try {
//          stage('checkout code') {
//           checkout scm
//          }
//          stage('extract data') {
//           bat "C:\\Users\\Dell\\AppData\\Local\\Programs\\Python\\Python314\\python.exe extract_data.py"
//          }
//     }
//     catch(err) {
//           echo "pipeline error : ${err}"
//     }
//     finally {
//         echo "pipeline completed"
//     }
// }
