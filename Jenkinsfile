pipeline {
    agent any
    tools {
        maven 'M2_HOME'
    }
    options {
        timeout(time: 5, unit: 'MINUTES')  // Timeout de 5 minutes
    }
    environment {
        APP_ENV = "DEV"
    }
    stages {
        stage('Code Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/mkh-dev/build-maven-project.git',
                credentialsId: 'jenkins-example-github-pat'  // ID des credentials GitHub
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
