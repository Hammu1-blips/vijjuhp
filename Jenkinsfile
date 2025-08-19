pipeline {
    agent any

    tools {
        maven 'Maven'   // This name must match the one you saved in Jenkins
        jdk 'Java'      // This name must match the one you saved in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Hammu1-blips/vijjuhp.git'
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
        success {
            echo '✅ Build, Test, and Package completed successfully!'
        }
        failure {
            echo '❌ Build failed. Check logs.'
        }
    }
}

