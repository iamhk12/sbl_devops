pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/iamhk12/sbl_devops.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building Java'
                bat 'javac Practical.java'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Java program'
                bat 'java Practical'
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up...'
            bat 'del Practical.class' // Clean up compiled class file
        }
    }
}
