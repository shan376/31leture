pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/shan376/31leture.git'
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

        stage('Deploy') {
            steps {
                sh 'mkdir -p /home/ubuntu/dev-deploy'
                sh 'cp target/*.jar /home/ubuntu/dev-deploy/'
            }
        }
    }
}
