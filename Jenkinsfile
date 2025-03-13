pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/skanda-gowda-10/PES1UG22CS200_Jenkins.git']]])
                
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o PES1UG22CS200-1 main.cpp' // Compiles C++ file
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './PES1UG22CS200-1' // Runs the compiled file
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed' // Post action in case of failure
        }
    }
}
