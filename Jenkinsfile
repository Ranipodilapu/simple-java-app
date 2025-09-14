pipeline {
    agent any

    tools {
        maven 'Maven3' // Make sure this Maven installation exists in Jenkins
        jdk 'open JDK11'   // Make sure this JDK installation exists in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Ranipodilapu/simple-java-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
