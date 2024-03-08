pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Simranmadhup/PES1UG21CS595_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS595-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                sh 'exit 1'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
