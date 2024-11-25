pipeline {
    agent { label 'docker-agent-python' }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm // Automatically checks out the repository
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building...'
                // Create a virtual environment and install packages
                sh '''
                python3 -m venv venv  # Create the virtual environment
                bash -c "source venv/bin/activate && pip install -r myapp/requirements.txt"
                '''
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing...'
                sh '''
                bash -c "source venv/bin/activate && cd myapp && python3 hello.py"
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
