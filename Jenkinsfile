@Library('shared-library') _
pipeline {
    agent any
    environment {
        DOCKER_CRED = 'dockerhub'
    }
    stages {
        stage("Checkout code") {
            steps {
                script {
                   scmCheck()
                }
            }
        }
        stage("Build image") {
            steps {
                script {
                    step.buildNum()
                    step.buildImage('darrs08')
                }
            }
        }
        stage("Push image") {
            steps {
                script {
                    step.pushImage()
                }
            }
          }        
        }
   }
