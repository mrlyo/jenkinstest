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
                bat('C:\\DEV\\jarfromgit\\start_jars.bat')
                //"cmd /c cd c:\\DEV\\jarfromgit & start_jars.bat".execute()
                //def Batchfile = 'C:/DEV/jarfromgit/' + 'start_jars.bat'
                // Runtime.runtime.exec(Batchfile)
                // 'C:/DEV/jarfromgit/start_jars.bat'.execute()

              //  def powershell = load 'C:\\DEV\\jarfromgit\\start_jars.bat'
               // powershell.exec('ls')




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
