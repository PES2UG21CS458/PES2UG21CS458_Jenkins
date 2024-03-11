pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: "GitSCM",
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/PES2UG21CS458/PES2UG21CS458_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES2UG21CS458-1'
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
                echo 'Deployment...'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
