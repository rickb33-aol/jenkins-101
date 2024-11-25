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
                // Create and activate a virtual environment, then install requirements
                sh '''
                python3 -m venv venv  # Create virtual environment
                source venv/bin/activate  # Activate the virtual environment
                pip install -r myapp/requirements.txt  # Install dependencies
                '''
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing...'
                sh '''
                source venv/bin/activate  # Activate the virtual environment again
                cd myapp
                python3 hello.py  # Run your application
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
