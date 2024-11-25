pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                // Checkout your repository code here
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'python3 -m venv venv' // Create virtual environment
                sh '''
                source venv/bin/activate
                pip install -r myapp/requirements.txt
                '''
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '''
                source venv/bin/activate
                cd myapp
                python3 hello.py
                '''
            }
        }
        
        stage('Deliver') {
            steps {
                echo 'Delivering...'
                // Add delivery steps here
            }
        }
    }
}
