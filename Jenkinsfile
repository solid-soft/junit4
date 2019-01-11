pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git poll: false, url: 'https://github.com/solid-soft/junit4.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn test"
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            } 
        }
    }
}
