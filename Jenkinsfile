#!/usr/bin/env groovy
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
                script {
                    sleep 1
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
        stage('Code Compilation') {
            steps {
               sh '''
               echo "Maven build: In Progress"
               mvn clean install
               '''
            }
        }
    }
}