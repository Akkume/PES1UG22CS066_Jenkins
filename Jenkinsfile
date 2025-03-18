pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Intentionally using a wrong file name to cause failure
                    sh 'g++ -o output hello_wrong.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}

