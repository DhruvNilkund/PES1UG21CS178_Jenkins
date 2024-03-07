pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    // branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/DhruvNilkund/PES1UG21CS178_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS178-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                error 
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
