pipeline {
    agent any

    options {
        timestamps()
        timeout(time: 5, unit: 'MINUTES')
    }

    stages {
        stage('Checkout Verification') {
            steps {
                echo 'Jenkins pipeline started successfully!'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Build Test') {
            steps {
                echo 'Running sample build test...'
                sh 'echo "Build test passed"'
            }
        }

        stage('Validation') {
            steps {
                sh 'test -f Jenkinsfile'
                echo 'Jenkinsfile exists in the workspace.'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: All sample tests passed.'
        }
        failure {
            echo 'FAILURE: Please check the Console Output.'
        }
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
