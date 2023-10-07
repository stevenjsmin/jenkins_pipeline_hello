#!/usr/bin/groovy
@Library(value='cicd-shared-libs@master', changelog=false) _

def echoMessage


pipeline {
    agent { node { label "master" } }

    options {
        ansiColor('xterm')
        timestamps()
        timeout(time: 1, unit: 'HOURS')
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage("Stage1") {
            steps {
                script {
                    echo "Hi from step1 of stage1"
                }
            }
        }
        
        stage("Stage2") {
            steps {
                script {
                    echo "AnNyoung from step of stage2"
                    echoMessage = ping()
                    echo echoMessage
                }
            }
        }
    } // End of Stages
    
    post {
        failure {
            script {
                echo "Run when failure"
            }
        }
        success {
            script {
                echo "Run when success"
            }
        }
    }
}
