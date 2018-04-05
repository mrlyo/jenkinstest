#!/usr/bin/env groovy

pipeline {
    agent any


    stages{
        stage('first stage'){
            steps{
                echo 'hello world'
            }
        }
        stage('Pull File'){
            steps{
                echo 'git pull ...'
                // Get some code from a GitHub repository
                git url: 'https://github.com/jglick/simple-maven-project-with-tests.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                script{
                    if (isUnix()) {
                        sh "mvn -Dmaven.test.failure.ignore clean package"
                    } else {
                        bat(/mvn -Dmaven.test.failure.ignore clean package/)
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}