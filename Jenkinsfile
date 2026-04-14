

pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Shalinij14/MyMavenSeleniumfirefoxApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        // Optional Test Stage (if needed)
        /*
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        */

        // Optional Run (not recommended for Jenkins)
        /*
        stage('Run Application') {
            steps {
                sh 'nohup java -jar target/MyMavenSeleniumfirefoxApp-1.0-SNAPSHOT.jar &'
            }
        }
        */
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
