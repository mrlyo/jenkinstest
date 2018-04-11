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

                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'C:\\DEV\\jarfromgit']], submoduleCfg: [], userRemoteConfigs: [[url: 'http://github.com/mrlyo/jaronly']]])
            }
        }
        stage('Starting App') {
            steps {
                echo 'starting..'
                bat('cmd /K C:\\DEV\\jarfromgit\\start_jars.bat')
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
