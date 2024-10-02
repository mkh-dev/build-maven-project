pipeline {
    agent any
    tools {
        maven 'M2_HOME'
    }
    options {
        timeout(time: 5, unit: 'MINUTES')  
    }
    environment {
        APP_ENV = "DEV"
    }
    stages {
        stage('Code Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/mkh-dev/build-maven-project.git'
            }
        }
        stage('Code Build') {
            steps {
                sh 'mvn install'
            }
        }
    }
    post {
        always {
            echo "======always======"
        }
        success {
            echo "=====pipeline executed successfully====="
        }
        failure {
            echo "======pipeline execution failed======"
        }
    }
}
