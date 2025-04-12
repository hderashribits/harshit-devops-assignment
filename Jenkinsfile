pipeline {
    agent any

    tools {
        jdk 'jdk-17' 
        maven 'maven-3.9.3'
    }

    environment {
        DEPLOY_ENV = 'development'
    }

    stages {
        stage('Preparation') {
            steps {
                echo 'Checking out source code...'
                git branch: 'main', url: 'https://github.com/hderashribits/harshit-devops-assignment.git'
                echo 'Cleaning previous builds...'
                sh 'mvn clean'
            }
        }

        stage('Deploy to Dev') {
            steps {
                echo 'Deploying to development environment...'
                sh 'echo Deploying to Dev Environment'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy to Prod') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to production environment...'
                sh 'echo Deploying to Production Environment'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed. Please check logs.'
        }
        always {
            echo 'Pipeline run completed.'
        }
    }
}














Y

