pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'Java17'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Hammu1-blips/vijjuhp.git',
                    credentialsId: 'github-cred'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        failure {
            echo "❌ Build failed. Check logs."
        }
        success {
            echo "✅ Build succeeded."
        }
    }
}
