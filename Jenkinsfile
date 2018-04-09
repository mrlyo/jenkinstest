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
              //  git url: 'https://github.com/mrlyo/sample'
                
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'C:\\DEV\\samplefromgit']], submoduleCfg: [], userRemoteConfigs: [[url: 'http://github.com/mrlyo/sample']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'

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
