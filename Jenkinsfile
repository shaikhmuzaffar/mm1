pipeline {

    options {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
    }

    agent {
                label "master"
            }
    stages {
        stage('Prerequisite Check') {
		  stage('Initialize') {
            steps {
               script {
			       sleep 20
                   def BUILD_BRANCH = env.BRANCH_NAME
                   def BUILD_BRANCH_TYPE = null
                   def BUILD_BRANCH_TASK = null
                   def BUILD_SHA1 = sh(script: 'git rev-parse HEAD', returnStdout: true).trim()
                   def BUILD_TAG = sh(script: "git tag -l --points-at HEAD", returnStdout: true).trim()
                   def BUILD_TYPE = null
                   def BUILD_VERSION = null
                   def matcher = BUILD_BRANCH =~ /(.*)\/(.*)/
                   def TAG_VERSION = BUILD_TAG.split( '-' )

                   env.BUILD_BRANCH = BUILD_BRANCH
                   env.BUILD_BRANCH_TYPE = BUILD_BRANCH_TYPE
                   env.BUILD_BRANCH_TASK = BUILD_BRANCH_TASK
                   env.BUILD_SHA1 = BUILD_SHA1
                   env.BUILD_TAG = BUILD_TAG
                   env.BUILD_VERSION = BUILD_VERSION
                   env.BUILD_TYPE = BUILD_TYPE
			   }
             }
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
                sh 'java -version'
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