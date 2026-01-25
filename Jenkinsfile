pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from Git'
                checkout scm
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests'
                bat 'python -m pip install pytest'          // ensure pytest is available
                bat 'python -m pytest test_calculator.py'  // run tests
            }
        }

        stage('Package') { 
    steps {
        echo 'Packaging the project'

        // Ensure setuptools and wheel are installed
        bat 'python -m pip install --upgrade setuptools wheel'

        // Build the wheel file
        bat 'python setup.py bdist_wheel'
    }
}

