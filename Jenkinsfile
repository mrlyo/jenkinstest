#!/usr/bin/env groovy

pipeline {
    agent any


    stages{
        stage('first stage'){
            steps{
                echo 'hello world'
            }
        }
    }

    /* stages {
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
                 if (isUnix()) {
                     sh "mvn -Dmaven.test.failure.ignore clean package"
                 } else {
                     bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
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
     }*/
}