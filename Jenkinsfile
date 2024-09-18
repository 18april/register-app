pipeline {
    agent any

    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
        stage("Checkout from Git") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/18april/register-app.git'
            }
        }
        stage("Build") {
            steps {
                sh "mvn clean package"
            }
        }
        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
