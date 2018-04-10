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
        stage('Build') {
            steps {
                echo 'Building..'
               // bat('java -jar  C:\\DEV\\jarfromgit\\sample-0.0.1-SNAPSHOT.jar &')
                //"cmd /c cd c:\\DEV\\jarfromgit & start_jars.bat".execute()
                //def Batchfile = 'C:/DEV/jarfromgit/' + 'start_jars.bat'
               // Runtime.runtime.exec(Batchfile)
               // 'C:/DEV/jarfromgit/start_jars.bat'.execute()
                GroovyShell shell = new GroovyShell()
                def script = shell.parse(new File('C:/DEV/jarfromgit/groovystart.groovy'))
                script.mymethod()


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
