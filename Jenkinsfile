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
                script {
                    sh './output'
                    sh 'echo 1'
                    sh 'echo 2'
                    sh 'echo 3'
                    sh 'echo 4'
                    sh 'echo 5'
                }
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

