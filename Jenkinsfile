pipeline {
    agent  { label 'windows' }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat 'pytest'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESS: All tests passed.'
        }

        failure {
            echo 'BUILD FAILURE: Tests or another stage failed.'
        }
    }
}

