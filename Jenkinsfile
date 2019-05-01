pipeline {

    options {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
    }

    agent {
                label "master"
            }
    stages {
        stage('Prerequisite Check') {
            steps {
                echo 'Hello, Maven'
                sh 'java -version'
            }
        }
        stage('Initialize') {
            steps {
                echo 'Hello, Maven'
                sh 'java -version'
            }
        }
        stage('Code Compilation') {
            steps {
                echo 'Hello, Maven'
                sh java -version'
            }
        }
        stage('Sonar Inspection') {
            steps {
                echo 'Hello, Maven'
                sh 'java -version'
            }
        }
        stage('QA Code Testing') {
            steps {
                echo 'Hello, Maven'
                sh 'java -version'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Hello, Maven'
                sh 'java -version'
            }
        }
        stage('Upload Image to ECR') {
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
        stage('Deploy to Prod') {
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}