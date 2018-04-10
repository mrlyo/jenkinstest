#!/usr/bin/env groovy

pipeline {
    agent any
    tools{
        maven 'maven'
        jdk 'jdk8'

    }

    stages{
        stage('first stage'){
            steps{
                echo 'hello world'
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
            }
        }
        stage('Pull File'){
            steps{
                echo 'git pull ...'
                // Get some code from a GitHub repository
                //  git url: 'https://github.com/mrlyo/sample'

                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'C:\\DEV\\samplefromgit']], submoduleCfg: [], userRemoteConfigs: [[url: 'http://github.com/mrlyo/jaronly']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                //bat('mvn clean install -f "C:\\DEV\\samplefromgit\\pom.xml"')

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
